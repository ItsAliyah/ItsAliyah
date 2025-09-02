# Hello World, it's Aliyah 👋  
I'm an **Aspiring Data Analyst Manager** with interests in data analytics, technology, and business strategy.  

---

## 🌟 About Me
- 🎓 Freshman at **Grambling State University**, majoring in CIS and minoring in Marketing  
- ⚾ Student-athlete balancing over 30+ hours of commitments weekly while exploring **sports analytics**  
- 📊 Passionate about using **data to drive decision-making**  

---

## 🔗 Connect with Me
- 💼 [LinkedIn](https://www.linkedin.com/in/aliyahd)  
- 📷 [Instagram](https://www.instagram.com/its.deet)  
- 📧 [Gmail](mailto:aliyahdugars@gmail.com)  

---

## 🛠 Skills
- **Data Tools:** Excel, Power BI, SQL basics  
- **Programming:** Python, JavaScript, HTML, CSS  
- **Business:** Marketing insights, project collaboration, and strategy  

---

## 🎵 Spotify API Project Example
```javascript
// Authorization token that must have been created previously. 
// See: https://developer.spotify.com/documentation/web-api/concepts/authorization

const token = 'YOUR_TOKEN_HERE'; 

async function fetchWebApi(endpoint, method, body) {
  const res = await fetch(`https://api.spotify.com/${endpoint}`, {
    headers: {
      Authorization: `Bearer ${token}`,
    },
    method,
    body: JSON.stringify(body)
  });
  return await res.json();
}

async function getTopTracks(){
  // Endpoint reference : https://developer.spotify.com/documentation/web-api/reference/get-users-top-artists-and-tracks
  return (await fetchWebApi(
    'v1/me/top/tracks?time_range=long_term&limit=5', 'GET'
  )).items;
}

const topTracks = await getTopTracks();
console.log(
  topTracks?.map(
    ({name, artists}) =>
      `${name} by ${artists.map(artist => artist.name).join(', ')}`
  )
);
