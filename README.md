from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext

# Command functions
def wc(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('WC Command triggered')

def smoke(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('SMOKE Command triggered')

def check_in(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('CHECK IN Command triggered')

def check_out(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('CHECK OUT Command triggered')

def back(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('BACK Command triggered')

def main():
    # Your Bot Token
    TOKEN = 'YOUR_BOT_TOKEN'
    
    # Set up the Updater and Dispatcher
    updater = Updater(TOKEN)
    dispatcher = updater.dispatcher
    
    # Add command handlers
    dispatcher.add_handler(CommandHandler('wc', wc))
    dispatcher.add_handler(CommandHandler('smoke', smoke))
    dispatcher.add_handler(CommandHandler('check_in', check_in))
    dispatcher.add_handler(CommandHandler('check_out', check_out))
    dispatcher.add_handler(CommandHandler('back', back))
    
    # Start the Bot
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()
