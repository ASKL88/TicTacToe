Tic-Tac-Toe Game

This project uses HTML, CSS, and JS to create a functional Tic-Tac-Toe game. HTML and CSS are used to create the layout and grid of the tic-tac-toe. JavaScript was used for all functionality of the game. 


This JS is needed for proper flow of the game and to determine the end:

      //This variable keeps track of who's turn it is.
      let activePlayer = 'X';
      //This array stores an array of moves. We use this to determine win conditions.
      let selectedSquares = [];


This JS is needed for each step of the game and for event handlers upon user input:

      //This function is for placing an x or o in a square.
      function placeXOrO(squareNumber) {
          //This condition ensures a square hasn't been selected already.
          //The .some() method is used to check each elementof selectedSquare array to
          //see if it contains the square number clicked on.
          if (!selectedSquares.some(element => element.includes(squareNumber))) {
              //This variable retrieves the html element id that was clicked.
              let select = document.getElementById(squareNumber);
              //This condition checks who's turn it is.
              if(activePlayer === 'X') {
                  //If activePlayer is equal to 'X', the x.png is placed in HTML.
                  select.style.backgroundImage = 'url("images/ex.jpg")';
              //Active player may only be 'X' or 'O' so, if not 'X' it must be 'O'
              } else {
                  //If activePlayer is equal to 'O', the o.png is placed in HTML.
                  select.style.backgroundImage = 'url("images/oh.jpg")';
              }
              //squareNumber and activePlayer are concatenated together and added to array.
              selectedSquares.push(squareNumber + activePlayer);
              //This calls a function to check for any win conditions.
              checkWinConditions();
              //This condition is for changing the active player.
              if (activePlayer === 'X') {
                  //If active player is 'X' change it to 'O'.
                  activePlayer = 'O';
              //If active player is anything other than 'X'.
              } else {
                  //Change the activePlayer to 'X'
                  activePlayer = 'X';
              }
              
              
This JS is needed for sound media to be used with user input:

      //This function plays placement sound.
      audio('./media/fart.mp3')
      //This condition checks to see if it is computer's turn.
      if(activePlayer === 'O') {
          //This function disables clicking for computer choice.
          disableClick();
          //This function waits 1 sec before placing the image and enabling click.
          setTimeout(function (){ computersTurn(); }, 1000);
      }
      //Returning true is needed for our computersTurn() function to work.
      return true;
              }
