

# Wiegand protocol reader for micropython

This library is essentially the Wiegand class, which allows the user to set
callbacks based on receiving a card number from a 
[weigand-protocol](https://en.wikipedia.org/wiki/Wiegand_interface) reader.

## Example usage:

    from wiegand import Wiegand

    VALID_CARDS = [ '12345' ]

    GREEN_LED = Pin(...)
    RED_LED = Pin(...)

    WIEGAND_ZERO = XX  # Pin number here
    WIEGAND_ONE = YY   # Pin number here

    def on_card(card_number, cards_read):
	if card_number in VALID_CARDS:
	    GREEN_LED.high()
	    RED_LED.low()
	else:
	    RED_LED.high()
	    GREEN_LED.low()
    
    
    Wiegand(WIEGAND_ZERO, WIEGAND_ONE, on_card)

