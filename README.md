## css-ticks

# Html Table in Zebra fromat with 3 colors

table tr td {
  border: 1px solid #333;
}

table tr:nth-child(n) {
  background-color: #fff;
  color: #000;
}
table tr:nth-child(2n) {
  background-color: #000;
  color: #fff;
}
table tr:nth-child(3n) {
    background-color: yellow;
    color: #fff;
}
