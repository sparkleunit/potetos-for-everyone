# C# formatting

Follow the repository's established style. When it leaves room for choice, use these preferences:

- Keep declarations together only when they form a readable setup block. Align assignments when nearby code does. Leave a blank line between declarations and the next action, even when there is only one declaration.
- Keep short calls on one line. When a call or nested call spans lines, break after each opening parenthesis, put arguments one per line, and put each closing parenthesis on its own line aligned with the invocation it closes. Wrap the outer call too when its lambda argument contains a multiline call.
- Leave a blank line after a completed multiline call before the next distinct action.

For example:

```csharp
var builder = Host.CreateApplicationBuilder(args);

builder.Services.AddHostedService(
    provider => new WorkerHostService(
        domain,
        provider.GetRequiredService<IConfiguration>(),
        provider.GetRequiredService<IHostApplicationLifetime>()
        )
    );

await builder.Build().RunAsync();
```

This captures the user's formatting example in `Common/Lib/WorkerHost.cs`; it is not a reason to reformat unrelated code or preserve incidental trailing whitespace.
