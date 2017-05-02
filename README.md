# JSCN Observables Workshop

Let's learn observables through a series of challenges.  **I strongly recommend** you avoid googling for relevant samples.  You'll learn better if you take the time to explore (and fail) on your own rather than copy-pasting.

## Getting started
```
npm install
npm start
```

# Challenge #1 - A Simple calculator

Learn the basics of observable event data sources.

Add the following elements to your application:
- A result field, displaying a sum starting at 0
- Two buttons: Add 1, Subtract 1
- When Add 1 is clicked, the sum total is incremented by 1.  When Subtract 1 is clicked, decrement by 1.
- A log of all operations that have occurred.
- BONUS: Add a "Square it" button which will multiply the sum total by itself.  Since this is such a "dangerous" operation, the user must press the button three times in rapid (within 1000 ms) succession.

### Sample Output

> [Add 1]    [Subtract 1]    [Square it]
>
> Log:
>   - ADD 1
>   - ADD 1
>   - ADD 1
>   - SUBTRACT 1
>   - SQUARE IT
> 
>  Total: 4

# Challenge #2 - Need some Zen?

Do you need some zen?  Use multiple api-driven observables to find out.

Create an application with a single button: "Need some Zen?".  When the button is pressed, a request should be made to `GET https://yesno.wtf/api`, which will assess your present state of mind and tell you if Zen is needed.

```
Sample API response:
{
	"answer": "no",
	"forced": false,
	"image": "https://yesno.wtf/assets/no/1-c7d128c95c1740ec76e120146c870f0b.gif"
}
```

If you do need Zen, a follow-up request should be made to `GET https://api.github.com/zen` to return your prescribed inspiration.

Since things happening quickly is clearly not Zen, the following optimizations can be considered:
- Request throttling to each API individually, or API requests globally
- Introduce a delay between button click and API request
- Slowly animate fade in/out effects (using observables of course!) for all messages
- Handle error scenarios.  If APIs are down or connectivity is lost, backup Zen should be applied.

