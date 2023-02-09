---
layout: essay
type: essay
title: "Squeaky Clean"
# All dates must be YYYY-MM-DD format!
date: 2023-03-07
published: true
labels:
- Software Programming
- Coding Standards
- ESLint
---

We've all seen instances of where a workspace wasn't in its best condition, whether it be from things not being put back where they belong, to the space simply not being cleaned. 

## The Importance of Cleanliness

Working in a messy environment is never the best option. While it may be okay for certain types of people, for most an unorganized environment is detrimental in keeping track of what one is doing. In programming especially, keeping your code organized is very important, as it helps whoever reads said code understand what it is that the code is trying to do. This helps not just others but also yourself, as when something goes wrong and the code needs to be fixed or debugged, it'll be a lot easier when you can understand the existing code.

## Love - Hate Relationship

I personally already try to keep my code organized. Not just because it functionally helps, but because I get very annoyed with messy code and keeping it nice and neat makes me happy. That's why I don't particularly mind using ESLint, because most of he coding standards that it enforces are things that I already do for the most part. That doesn't mean that I don't have any issues with ESLint at all, though. There have already been instances where I write some code and get that annoying error message despite the code looking good and working perfectly fine for what I was trying to do.  
The following code produces an error with ESLint, despite the code working fine.

```
function ziplist(arr1, arr2) {
  const newArray = [];
  for (const key in arr1) {
    newArray.push(arr1[key]);
    newArray.push(arr2[key]);
  }
  return newArray;
}
```
The solution to the error was:
```
function ziplist(arr1, arr2) {
  const newArray = [];
  for (const key in arr1) {
    if ({}.hasOwnProperty.call(arr1, key)) {
      newArray.push(arr1[key]);
      newArray.push(arr2[key]);
    }
  }
  return newArray;
}
```
This was very annoying to deal with because the ESLint did not suggest this as a fix, instead suggesting to suppress the error with a comment. In order to fix the error, I had to google the error and look up ways to fix it. While it may not be that big of a deal due to this particular code being simple, it may be much more annoying if the code is more complex, requiring a more complex solution.

## Overall Impression

I can definitely see how some people can have issues with ESLint, particularly at the beginning if they are not used to using some sort of coding standard. However, I do agree that following a coding standard will help people learn how to code, for both the person writing the code and the people who might read the code. Standardized code creates an environment that is much easier to work in and learn from. After all, the hardest thing to learn is something that doesn't have a standard and varies a lot from instance to instance.
