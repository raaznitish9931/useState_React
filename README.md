# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

#explanation

// React aur useState hook ko import kar rahe hain
import React, { useState } from 'react';

// Button naam ka functional component banaya hai
function Button() {

    // useState ka use karte hue 'val' naam ki state ko initialize kar rahe hain
    // 'val' ek object hai jisme 'name' aur 'isBanned' properties hain
    const [val, setVal] = useState({ name: "nitish", isBanned: false });

    return (
        // Yeh div full-screen ko cover karega aur content ko center mein display karega
        <div className='h-screen w-full p-5 flex items-center flex-col justify-center'>
            
            {/* name ko display karte hain */}
            <h1 className='font-semi-bold text-4xl'>
                name: {val.name} {/* val.name ko display karenge jo "nitish" hai */}
            </h1>

            {/* isBanned ko display karte hain, aur usko string mein convert kar rahe hain */}
            <h2 className=' text-3xl'>
                banned: {val.isBanned.toString()} {/* val.isBanned ko display karenge, jo initially 'false' hai */}
            </h2>

            {/* Button jo state ko update karega */}
            <button 
                // onClick event, jab button click ho, state update karega
                onClick={() => setVal({ ...val, isBanned: !val.isBanned })}
                className='px-2 text-m py-1 bg-blue-600 text-white rounded-md mt-5'
            >
                Change {/* Button ka text */}
            </button>

        </div>
    );
}

// Button component ko export kar rahe hain taaki use kisi aur file mein kiya ja sake
export default Button;
