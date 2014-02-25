# robotlegs2-starling-extension

Starling extension for Robotlegs2 (RL2)

## Description

Copy src directory to yours.
Externals directory is made from external projects. So it is not my code.

## Usage

```
new Context()
  .install(MVCSBundle)
  .install(SignalCommandMapExtension)
  .install(StarlingExtension)
  .configure(_starling);
```

```
// mediator
class FooViewMediator extends StarlingMediator
{
    [Inject]
    public var fooHappened:FooHappened;

    [Inject]
    public var view:FooView; // it is a starling sprite

    override public function initialize():void
    {
        // signal map
        signalMap.mapListener(fooHappened, onFooHappen);

	// starling event map
        eventMap.mapStarlingEvent(view.button, Event.TRIGGERED, onButtonTrigger);
    }

    private function onFooHappen():void
    {
        // ...
    }

    private function onButtonTrigger():void
    {
        // ...
    }
}
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
