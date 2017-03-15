# Test Project

This project is used for testing various build and release process changes.

# DropWizard Async Support

This bundle adds support for resources methods to return `CompletionStage`. The methods will be automatically converted to asynchronous
resources (as if the `@Suspended` annotation were used on them), and Jersey will wait for the `CompletionStage` to settle before resuming
with the result of the stage.

To use this bundle, add it to your application in the initialize method:

    @Override
    public void initialize(Bootstrap<YourConfig> bootstrap) {
        bootstrap.addBundle(new CompletionStageBundle());
    }
