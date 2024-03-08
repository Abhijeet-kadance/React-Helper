## Props Concepts

    => Forwaded Props
    => Multiple Component Slot
    => Element Identifiers as Props
    => Default Prop Values

## Example 

    import Button from './Button';
    import HomeIcon from './HomeIcon';
    import PlusIcon from './PlusIcon';

    function App() {
    return (
        <div id="app">
        <section>
            <h2>Filled Button (Default)</h2>
            <p>
            <Button>Default</Button>
            </p>
            <p>
            <Button mode="filled">Filled (Default)</Button>
            </p>
        </section>
        <section>
            <h2>Button with Outline</h2>
            <p>
            <Button mode="outline">Outline</Button>
            </p>
        </section>
        <section>
            <h2>Text-only Button</h2>
            <p>
            <Button mode="text">Text</Button>
            </p>
        </section>
        <section>
            <h2>Button with Icon</h2>
            <p>
            <Button Icon={HomeIcon}>Home</Button>
            </p>
            <p>
            <Button Icon={PlusIcon} mode="text">
                Add
            </Button>
            </p>
        </section>
        <section>
            <h2>Buttons Should Support Any Props</h2>
            <p>
            <Button mode="filled" disabled>
                Disabled
            </Button>
            </p>
            <p>
            <Button onClick={() => console.log('Clicked!')}>Click me</Button>
            </p>
        </section>
        </div>
    );
    }

    export default App;
---
---
    // Button.js file

        export default function Button({mode = "filled" , children , Icon, ...props}) {
        // Todo: Build this component!
        
        let cssclass = `button ${mode}-button`
        
        if(Icon){
            cssclass += ' icon-button'
        }
        
        if(props.className){
            cssclass += ' ' + props.className
        }

        return(<>
                    <button className={cssclass} {...props} > 
                    {Icon && (<span className="button-icon">
                                <Icon />
                            </span>
                    )}
                        <span>{children}</span> 
                    
                    </button>
                </>)
        // !!! Important: 
        // Wrap the icon with a <span className="button-icon"> to achieve the target look
        // Also wrap the children prop with a <span>
        }
---

***Just like this The PlusIcon and HomeIcon are just SVG file component that return svg icons that can be used as icon in a button***