# Next.js 15 App Router: Conflicting Static and Server-Side Props

This repository demonstrates a bug in Next.js 15's App Router where using both `getServerSideProps` and `getStaticProps` in a single page results in unexpected behavior and an error.

## Bug Description

When attempting to fetch data using both `getServerSideProps` and `getStaticProps` in a page within the App Router, the application throws an error.  The expected behavior is that either one or the other function should be used, and using both simultaneously should be prevented or result in a clear error message indicating this conflict.

## Reproduction Steps

1. Clone this repository.
2. Install dependencies using `npm install`.
3. Run the development server using `npm run dev`.
4. Observe the error in the console.

## Expected Behavior

The application should either prevent the use of both `getServerSideProps` and `getStaticProps` simultaneously, or handle this conflict gracefully by throwing a clear, informative error message.

## Actual Behavior

The application throws an error, indicating a conflict or incorrect behavior, potentially due to the combination of both functions.

## Solution

Choose either `getServerSideProps` or `getStaticProps` and remove the other.  If dynamic data is needed for every request, use `getServerSideProps`. If data does not change frequently and can be pre-rendered, use `getStaticProps`.