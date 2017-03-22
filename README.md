public class Cards{
        
   public String [] cards= new String[52];
   int cardsDealt = 0;

   public void shuffle() {
      String [] suit = {"hearts", "Spades", "Clubs", "Diamonds"};
      String [] face = {"Ace of ", "2 of ", "3 of ", "4 of ", "5 of ", "6 of ", "7 of ", "8 of ", "9 of ", "10 of ", "Jack of ", "Queen of ", "King of "};
      for (int s = 0; s < 4; s++) {
         for (int f = 0; f < 13; f++) {
            cards[s*13 + f] = face[f] + suit[s];
         }
      }
   }

   public String dealOneCard() {
      if (cardsDealt <52) {
         int i = (int) (Math.random () * 52);
         cardsDealt = cardsDealt + 1;
         return cards[i];
      }
      else {;
         return ("End of Deck");
      }
   }
        
   public void dealDeck() {
      for(int i = 0; i<cards.length; i++){
         System.out.println(cards[i]);
      }
   }
       
   public static void main (String []args) {

      Cards deck = new Cards ();

      deck.shuffle();

      System.out.println("Deck of Cards ");
      deck.dealDeck();

      System.out.println("Random Deck ");
      for (int i=0; i<53; i++){   
         System.out.println( deck.dealOneCard() );
      }
   }

}

