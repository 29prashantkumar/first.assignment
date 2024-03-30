# first.assignment
import { useState } from 'react';
import Head from 'next/head';

const Home = () => {
  const [darkMode, setDarkMode] = useState(false);

  const toggleTheme = () => {
    setDarkMode((prevDarkMode) => !prevDarkMode);
    document.documentElement.classList.toggle('dark');
  };

  return (
    <div className={`flex flex-col items-center justify-center min-h-screen ${darkMode ? 'dark' : ''}`}>
      <Head>
        <title>Theme Switcher</title>
        <link rel="icon" href="/favicon.ico" />
      </Head>

      <button
        className="fixed top-4 right-4 bg-gray-800 dark:bg-white p-2 rounded-full focus:outline-none"
        onClick={toggleTheme}
      >
        {darkMode ? (
          <svg
            xmlns="http://www.w3.org/2000/svg"
            className="h-6 w-6 text-yellow-500"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              strokeLinecap="round"
              strokeLinejoin="round"
              strokeWidth={2}
              d="M12 6v6m0 0v6m0-6h6m-6 0H6"
            />
          </svg>
        ) : (
          <svg
            xmlns="http://www.w3.org/2000/svg"
            className="h-6 w-6 text-gray-800 dark:text-yellow-500"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              strokeLinecap="round"
              strokeLinejoin="round"
              strokeWidth={2}
              d="M19 12a7 7 0 01-7 7 7 7 0 110-14 7 7 0 017 7zm0 0V5.999m0 0L19 3m0 8h2m-2 0h-2"
            />
          </svg>
        )}
      </button>

      <main className="flex flex-col items-center justify-center w-full flex-1 px-20 text-center">
        <h1 className="text-3xl font-bold text-white dark:text-yellow-500">
          Welcome to My Theme Switcher App
        </h1>
        <p className="text-xl text-white dark:text-yellow-400 mt-4">
          Try switching between light and dark modes!
        </p>
      </main>
    </div>
  );
};

export default Home;
