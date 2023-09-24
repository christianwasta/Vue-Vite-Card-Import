<template>
  <button id="btn">Duplicator</button>
  <button id="backgroundColor">Change Background Color</button>
  <button id="changeHeading">Change Heading Text</button>
  <button id="dltbtn">DeleteCard</button>
  <div class="card">
    <img alt="Picture of Card" src="https://images.unsplash.com/photo-1586957960772-3e526c5e7cbd?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTM0OTY0NDF8&ixlib=rb-4.0.3&q=85">
    <div class="card-content"> 
      <h2>Christian Wasta</h2> 
      <p id="Description"> HAX is a paradigm shift for web publishing. It puts advanced authoring capabilities in the hands of everyone, regardless of technical ability and all items made are sustainability built in highly semantic HTML.</p> 
      <button class="details-button" id="detailsBtn">Details</button>
    </div> 
  </div> 
  
  
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    document.querySelector('#btn').addEventListener('click', () => {
      const clone = document.querySelector('.card').cloneNode(true); // Clone the whole card
      document.body.appendChild(clone);
    });
    
    document.querySelector('#backgroundColor').addEventListener('click', () => {
      const elem = document.querySelector(".card");
      const backgroundColor = elem.style.backgroundColor;

      if (backgroundColor === 'beige') {
        elem.style.backgroundColor = 'green';
      } else {
        elem.style.backgroundColor = 'beige';
      }
    });
    
    // HEADING CHANGER
    document.querySelector('#changeHeading').addEventListener('click', () => {
      const title = document.querySelector('h2');
      title.innerText = "Christian Wasta Alt Title";
    });
    
    // Card delete
    document.querySelector('#dltbtn').addEventListener('click', () => {
      const cards = document.querySelectorAll('.card');
      // Check if there are cards to delete
      if (cards.length > 1) {
        const lastCard = cards[cards.length - 1];
        lastCard.parentNode.removeChild(lastCard);
      }
    });
    
    var original = document.querySelector('#description').innerText;
    
    document.querySelector('#detailsBtn').addEventListener('click', () => {
      const description = document.querySelector('#description');
      // Toggle the visibility of the description
      if (description.innerText === 'none' || description.innerText === '') {
        description.innerText = original; // Show the description
      } else {
        description.innerText = ''; // Hide the description
      }
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.card{
  margin: 0 auto;
  max-width: 300px;
  max-height: 400px;
  min-height: 10px;
  padding: 8px 8px 37px 8px;
  border-radius: 10px;
  overflow: shown;
  background-color: beige;
}

.card img {
  max-width: 100%;
  height: auto;
}

.card-content {
  flex: 1;
}

/* Style for the Title label */
h2 {
  font-size: 24px;
  margin: -10px 0;
  /* Background color and border */
  background-color: black;
  /* Background color */
  color: #fff;
  /* Text color on the background */
  padding: 8px 16px;
  border-radius: 4px;
}

p {
  font-size: 16px;
  margin: 8px 0;
  color: black;
}

a.details-button {
  background-color: #EA5F0A;
  color: #fff;
  padding: 8px 16px;
  text-decoration: none;
  border-radius: 4px;
}
</style>
