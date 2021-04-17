# RandomPasswordGenerator

This action generates a random password.
It will contain at least one non-capital, one capital, one number and one special character.
It will not contain similar characters (like I & l)

Note: There is a good chance of this string being exposed somewhere in the logs when another step uses it. So use with care! This is best suited for lab/demo purposes or temporary passwords.

To use the created string, call the output in a separate action with the following syntax:
```${{ steps.[stepID].outputs.password }}```

## example usage

```yml
     - uses: actions/checkout@v2
     - id: generatedpassword
       uses: aammirmirza/RandomPasswordGenerator@v1.1
       with:
        length: 15
     - run: echo "${{ steps.generated-password.outputs.password }}"
       shell: bash
```
