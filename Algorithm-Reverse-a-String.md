# Problem Explanation:
We need to take the string and reverse it, so if it originally reads 'hello', it will now read 'olleh'. We will need to split the string, and therefore we will be working with Arrays as well.

## Hint: 1
- Start by splitting the string by characters.

## Hint: 2
- Look up the built in function to reverse a string.

## Hint: 3
- Do not forget to join the characters back together after you reverse them.

## Spoiler Alert!
[![687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/thumb/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)](https://files.gitter.im/FreeCodeCamp/Wiki/nlOm/687474703a2f2f7777772e796f75726472756d2e636f6d2f796f75726472756d2f696d616765732f323030372f31302f31302f7265645f7761726e696e675f7369676e5f322e676966.gif)

**Solution ahead!**

## Code Solution:

```js
function reverseString(str) {
  return str.split('').reverse().join('');
}
```

# Code Explanation:
- Our goal is to take the input, `str`, and return it in reverse. Our first step is to split the string by characters using `split('')`. Notice that we don't leave anything in between the single quotes, this tells the function to split the string by each character.

- Using the `split()` function will turn our string into an array of characters, keep that in mind as we move forward.

- Next we *chain* the `reverse()` function, which takes our array of characters and reverses them.

- Finally, we *chain* `join('')` to put our characters back together into a string. Notice once again that we left no spaces in the argument for join, this makes sure that the array of characters is joined back together by each character.

# Credits:
If you found this page useful, you can give thanks by copying and pasting this on the main chat: **`Thanks @Rafase282 for your help with Algorithm: Reverse a String`**

> **NOTE:** Please add your username only if you have added any **relevant main contents** to the wiki page. (Please don't remove any existing usernames.)
