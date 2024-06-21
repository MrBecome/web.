# web.
// frontend/src/App.js

import React, { useState } from 'react';
import './App.css';

const App = () => {
  const [elements, setElements] = useState([]);

  const addTextElement = () => {
    const newTextElement = {
      type: 'text',
      content: 'Editable text',
      id: elements.length + 1
    };
    setElements([...elements, newTextElement]);
  };

  const addImageElement = () => {
    const newImageElement = {
      type: 'image',
      src: 'placeholder.jpg',
      alt: 'Placeholder Image',
      id: elements.length + 1
    };
    setElements([...elements, newImageElement]);
  };

  return (
    <div className="App">
      <header>
        <h1>Website Builder App</h1>
      </header>
      <main>
        <section className="editor">
          <div className="toolbar">
            <button onClick={addTextElement}>Add Text</button>
            <button onClick={addImageElement}>Add Image</button>
            {/* Add more tools for video, layout, etc. */}
          </div>
          <div className="canvas">
            {elements.map(element => (
              <div key={element.id} className={element.type}>
                {element.type === 'text' ? (
                  <div contentEditable>{element.content}</div>
                ) : (
                  <img src={element.src} alt={element.alt} />
                )}
              </div>
            ))}
          </div>
        </section>
      </main>
      <footer>
        <p>&copy; 2024 Website Builder App</p>
      </footer>
    </div>
  );
};

export default App;


