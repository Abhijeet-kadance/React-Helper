## Option 1

    const [selectedTopic, setselectedTopic] = useState()
                            OR
    const [selectedTopic, setselectedTopic] = useState("value")

    function handleSelect(selectedComponent){
        # example function to set useState value
        setselectedTopic(selectedComponent)
    }

    # Inside render of component 

    {!selectedTopic && "Please Select a button ..."}

    {selectedTopic && ( 
            <div id="tab-content">
              <h3>{EXAMPLES[selectedTopic].title}</h3>
              <p>{EXAMPLES[selectedTopic].description}</p>
              <pre>
                <code>
                {EXAMPLES[selectedTopic].code}
                </code>
              </pre>
            </div>
     ) 
    }


## Option 2

    const [selectedTopic, setselectedTopic] = useState()
                            OR
    const [selectedTopic, setselectedTopic] = useState("value")

    function handleSelect(selectedComponent){
        # example function to set useState value
        setselectedTopic(selectedComponent)
    }

    # Inside render of component 

    {!selectedTopic ? "Please Select a button ..." : null}
    {selectedTopic ? ( 
                <div id="tab-content">
                <h3>{EXAMPLES[selectedTopic].title}</h3>
                <p>{EXAMPLES[selectedTopic].description}</p>
                <pre>
                    <code>
                    {EXAMPLES[selectedTopic].code}
                    </code>
                </pre>
                </div>
        ) : null 
    }


## Option 3

    const [selectedTopic, setselectedTopic] = useState()

    let TopicData = "Please Select a button ..."

    if(selectedTopic){
        TopicData = ( 
                <div id="tab-content">
                <h3>{EXAMPLES[selectedTopic].title}</h3>
                <p>{EXAMPLES[selectedTopic].description}</p>
                <pre>
                    <code>
                    {EXAMPLES[selectedTopic].code}
                    </code>
                </pre>
                </div>
        )
    }

    function handleSelect(selectedComponent){
        setselectedTopic(selectedComponent)
    }

    # Inside render of component 

    {TopicData}