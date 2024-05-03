# jogo
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body{
    height: 100vh;
    width: 100vw;
    background: linear-gradient(
        90deg,
     rgb(197, 143, 237) 0%,
     rgb(245, 246, 247) 100%
     );
}

.board{
    display: grid;
    width: 100%;
    height: 100%;
    display: grid;
    justify-content: center;
    align-content: center;
    justify-items: center;
    align-items: center;
    grid-template-columns: repeat(3, auto);
}

.board.x .cell:not(.x):not(.circle):hover::after, 
.board.x .cell:not(.x):not(.circle):hover::before,
 .board.circle .cell:not(.x):not(.circle):hover::after, 
 .board.x .cell:not(.x):not(.circle):hover::before {
    background: rgba(255, 255, 255, 0.3) !important;
}

/* Célula */
.cell{
    width: 100px;
    height: 100px;
border: 2px solid white;
display: flex;
justify-content: center;
align-items: center;
position: relative;
}

.cell.x, .cell.circle {
cursor: not-allowed;
}

.cell:nth-child(1),
.cell:nth-child(2),
.cell:nth-child(3) {
border-top: none;
}

.cell:nth-child(1),
.cell:nth-child(4),
.cell:nth-child(7) {
border-left: none;
}

.cell:nth-child(7),
.cell:nth-child(8),
.cell:nth-child(9) {
border-bottom: none;
}


.cell:nth-child(3),
.cell:nth-child(6),
.cell:nth-child(9) {
border-right: none;
}

/* X */
.cell.x::before,
.cell.x::after,
.board.x .cell:not(.x):not(.circle):hover::after, 
.board.x .cell:not(.x):not(.circle):hover::before {
 content: "";
 height: calc(100px * 0.15);
 width: calc(100px * 0.9);
 background: white;
 position: absolute;
}

.cell.x::before,
.board.x .cell:not(.x):not(.circle):hover::before {
transform: rotate(45deg);
}

.cell.x::after,
.board.x .cell:not(.x):not(.circle):hover::after{
    transform: rotate(-45deg);
}

/* Circle */
.cell.circle::before,
.cell.circle::after,
.board.circle .cell:not(.x):not(.circle):hover::after, 
.board.circle .cell:not(.x):not(.circle):hover::after {
content: "";
height: calc(100px * 0.9);
width: calc(100px * 0.9);
background: white;
position: absolute;
border-radius: 50%;
}

/* Mensagem de Vitória */
.winning-message{
    display: none;
    position: fixed;
 top: 0;
 left: 0;
 right: 0;
 bottom: 0;
 justify-content: center;
 align-items: center;
 background-color: rgba(0, 0, 0, 0.8);
 flex-direction: column;
}

.winning-message-button {
font-size: 2.5rem;
background-color: rgb(167, 95, 235);
padding: 10px 15px;
cursor: pointer;
border-radius: 5px;
border: none;
margin-top: 16px;
color: white;
}

.winning-message-button:hover {
    color:  rgb(167, 95, 235);
    background-color: white;
}

.winning-message-text {
    color: white;
    font-size: 5rem;
}

.show-winning-message {
    display: flex;
}
