###  [Task 6 kyu](https://www.codewars.com/kata/55b350026cc02ac1a7000032/train/java)
Hereinafter, [space] refers to " ", [tab] refers to "\t", and [LF] refers to "\n" for illustrative purposes. This does not mean that you can use these placeholders in your solution.

In esoteric language called Whitespace, numbers are represented in the following format:

    first character represents the sign: [space] for plus, [tab] for minus;
    characters after that are the binary representation of the absolute value of the number, with [space] for 0, [tab] for 1, the rightmost bit is the least significand bit, and no leading zero bits.
    the binary representation is immediately followed by [LF].

Notes

    Valid Whitespace number must always have at least two characters: a sign and the terminator. In case there are only two characters, the number is equal to zero.
    For the purposes of this kata, zero must always be represented as [space][LF].
    In Whitespace, only space, tabulation and linefeed are meaningful characters. All other characters are ignored. However, for the purposes of this simple kata, please do not add any other characters in the output.
    In this kata, input will always be a valid negative or positive integer.
    For your convenience, in this kata we will use unbleach() function when evaluating your results. This function replaces whitespace characters with [space], [tab], and [LF] to make fail messages more obvious. You can see how it works in Example Test Cases.


### My solution
```Java
public class Kata {
    public static String whitespaceNumber(final int n) {
        if(n==0) return " \n";
        StringBuilder sBuilder = new StringBuilder();
        int posValue = 0;
        if(n<0){
            sBuilder.append("\t");
            posValue = -n;
        } else {
            sBuilder.append(" ");
            posValue = n;
        }
        String result = sBuilder.append(Integer.toBinaryString(posValue))
                .toString()
                .replace("0", " ")
                .replace("1", "\t")
                .concat("\n");
        return result;
    }
}

```

### Fav solution
```Java
class Kata {
  static String whitespaceNumber(int n) {
    return (n > 0 ? ' ' : n < 0 ? '\t' : "") + Integer.toBinaryString(Math.abs(n)).replace('0', ' ').replace('1', '\t') + '\n';
  }
}
```
I like this solution because I like it
