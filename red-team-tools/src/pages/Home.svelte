<script lang="ts">
    import SearchTools from '../components/SearchTools.svelte';
    import Category from '../components/Category.svelte';
    
    let toolCategories = [
      {
        name: 'Reconnaissance',
        tools: [
          { name: 'Nmap', description: 'Network exploration tool and security / port scanner' },
          { name: 'Wireshark', description: 'Network protocol analyzer' },
          { name: 'Maltego', description: 'Interactive data mining tool' },
          // ... more tools
        ]
      },
      {
        name: 'Exploitation',
        tools: [
          { name: 'Metasploit', description: 'Penetration testing framework for exploit development and execution' },
          { name: 'Burp Suite', description: 'Integrated platform for performing security testing of web applications' },
          // ... more tools
        ]
      },
      // ... more categories
    ];
  
    const performSearch = (event) => {
      console.log('Searching for:', event.detail.term);
    };
  </script>
  
  <main>
    <div class="content">
      <h1>Welcome to Your Toolkit!</h1>
      <SearchTools on:search={performSearch} />
      {#each toolCategories as category}
        <Category name={category.name} tools={category.tools} />
      {/each}
    </div>
  </main>
  
  <style>
    :global(body) {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(145deg, #0d0d0d, #262626);
      color: #ccc;
      height: 100vh;
      width: 100vw;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: auto;
    }
  
    main {
      display: block; /* Use block instead of flex to stack children */
      width: 90%; /* Use 90% of the viewport width */
      max-width: 80rem; /* Set to a maximum width for very large displays */
      margin: 3vh auto; /* Center the main container with vertical margin for breathing space */
      padding: 2rem;
      border-radius: 10px;
      background: rgba(0, 0, 0, 0.85); /* Darker background for main content */
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
      color: #e0e0e0;
      overflow: hidden; /* Ensure no content overflows the rounded corners */
      transition: transform 0.2s ease-in-out; /* Smooth transition for hover effect */
    }
  
    main:hover {
      transform: scale(1.01);
    }
  
    @media (max-width: 768px) {
      main {
        width: 95%;
        margin-top: 5vh;
        margin-bottom: 5vh;
      }
    }
  
    h1 {
      color: #fff;
      margin-bottom: 2rem;
    }
  
    .content {
      width: 100%;
      padding-bottom: 2rem;
    }
  
    footer {
      width: 100%;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      padding: 0.5rem 1rem;
      text-align: center;
    }
  
    footer p {
      font-size: 0.9rem;
      color: #999;
    }

  </style>
  