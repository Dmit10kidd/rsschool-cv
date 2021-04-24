## 1)Khodakov Dmitry
## 2)Telegram: __https://t.me/dimkanedimon__ / Email : __hoddima8@gmail.com__
## 3)I wish to start creating programs for ios devices cuz it's more interesting than development on Python for example and more demanded in market.
## 4) Python, telebot, mongodb, useragent and e.t.c python libraries

## 5)    

    def get_tor_session():   
        os.startfile(r'Укажите путь до файла tor.exe')
        session = requests.session()
        session.proxies = {'http':  'socks5://127.0.0.1:9050',
                   'https': 'socks5://127.0.0.1:9050'}               
        return session
        
    @bot.message_handler(commands=['start'])
    def privetctive(message):
        sent = bot.send_message(message.chat.id, "Здравствуйте, какой номер телефона?")
        bot.register_next_step_handler(sent, Nomer)

    @bot.message_handler(content_type=['voice'])
    def voice(message):
        try:
            file_info = bot.get_file(message.voice.file_id)
            file = requests.get('https://api.telegram.org/file/bot{0}/{1}'.format(config.token, file_info.file_path))
            with shelve.open('database' ,'c') as f: 
                f[key] = file_info
            keyboard2_1 = types.ReplyKeyboardMarkup(True,True)
            button2_1 = types.KeyboardButton(text ='Начать сначала')
            keyboard2_1.add(button2_1)    
            bot.send_message(message.chat.id, 'Голосовое сохранено под названием: {0}'.format(str(key)), reply_markup= keyboard2_1)
            bot.register_next_step_handler_by_chat_id(message.chat.id, start_message)
        except:
            bot.send_message(message.chat.id, 'Произошла ошибка,попробуйте ещё раз',)
            bot.register_next_step_handler_by_chat_id(message.chat.id, voice)
            
## 6)  __https://github.com/Dmit10kidd__
## 7) **Multifield college based on Tyumen Industrial University** *Tyumen, Russia, 2017-2019* **Graduated on speciality: Radio communication, broadcasting and television**
## 8) I'm studying English from 1st class of elementary school and self-study by watching films, playing videogames and practice with native speakers.
