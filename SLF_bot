import telebot
import random
import requests
from telebot import types

AD = [ """Встречаются двое сталкеров ну и один говорит:
— На днях к Долгу заходил…
— Ну и? (вопрошает)
— Чо и? (недовольный) И остался должен. Ха. А потом зашел к Свободе…
— Ну и чо?
— И стал СВОБОДЕН!""",
       """Студент на экзамене:
— Профессор, понимаете (томным голосом), я не могу сдать математику… потому что совсем не сплю в последний месяц. Вот только закрою глаза как появляется страшная картина… меня прижали к стене атомной станции какие-то страшные мутанты и готовы разорвать… в клочки.
А профессор говорит:
— Ха (злая ухмылка). Окончив институт с теперешними знаниями, молодой человек, наверняка, вы подались бы в сталкеры… а там и до ужаса, который вы увидели, совсем недалеко (читает нотацию). Да (улыбается), но у меня есть верное средство.
Поскольку переэкзаменовка по математике так и не сдана, то (строго) вы будете отчислены и пойдете служить. И никаких монстров (радостно), кроме, разве что, «дедов».""",
       """Допрашивает как-то «погонник» опытного сталкерюгу:
— То есть вы признаете (официальным тоном), что в нетрезвом виде пытались покинуть территорию Зоны, в районе 12-го блок-поста и имели при себе запрещенные к выносу за ее пределы предметы (вопрошает)?
Ну того запарило третий час под конвоем сидеть… Он и ему говорит:
— Так… я! Признаю, командир (почти крича)! Все признаю — вот те крест! Был бы трезвый — (недовольно скалится и выделяя каждое слово) я бы в жизни, мимо вас, уродов, с хабаром бы не поперся.""",
       """Бродит, говорят, по зоне ходячая аномалия — непьющий и некурящий сталкер.
«Приманивается на запах молочка или манной каши. Способ дистанционного обнаружения — на расстоянии 200 метров от объекта… счетчик Гейгера зашкаливает.»"""]

token = "738746294:AAGSpgcc5oYFj40tUYhcb0dOs3NspRDCvD8"

# Обходим блокировку с помощью прокси
telebot.apihelper.proxy = {'https': 'socks5://geek:socks@t.geekclass.ru:7777'}

# подключаемся к телеграму
bot = telebot.TeleBot(token=token)

def get_keyboard():
    keyboard = types.ReplyKeyboardMarkup()

    # добавляем на нее две кнопки
    button1 = types.KeyboardButton(text="/help")
    button2 = types.KeyboardButton(text="/anek")
    button3 = types.KeyboardButton(text="/Set")
    button4 = types.KeyboardButton(text="/bird")
    button5 = types.KeyboardButton(text="/Photo")
    keyboard.add(button1)
    keyboard.add(button2)
    keyboard.add(button3)
    keyboard.add(button4)
    keyboard.add(button5)

    return keyboard

@bot.message_handler(content_types=['photo'])
def qr(message):
    print("got photo")
    user_id = message.chat.id
    
    file_id = message.photo[-1].file_id
    
    path = bot.get_file(file_id)
    p = 'https://api.telegram.org/file/bot{0}/'.format(token) + path.file_path
    url = 'http://api.qrserver.com/v1/read-qr-code/'
    res = requests.post(url, {'fileurl': p})
    x = res.json()[0]['symbol'][0]['data']
    print (x)
    if x == AlexWasHere
    bot.send_message(user, "https://github.com/HungerPro/SLF_bot", reply_markup=get_keyboard())
    
# реагируем на команду /help
@bot.message_handler(commands=['help'])
def help(message):
    user = message.chat.id
    bot.send_message(user, "Напиши команду /anek, /bird или /Set и посмотри что будет", reply_markup=get_keyboard())
    
@bot.message_handler(commands=['anek'])
def anek(message):
    print("anek")
    user = message.chat.id
    bot.send_message(user, random.choice(AD), reply_markup=get_keyboard())

@bot.message_handler(commands=['But'])
def repeat_all_messages(message):
    # создаем клавиатуру
    
    # отправляем сообщение пользователю
    bot.send_message(message.chat.id, "Нажмите кнопку!", reply_markup=get_keyboard())

# функция запустится, когда пользователь нажмет на кнопку
@bot.callback_query_handler(func=lambda call: True)
def callback_inline(call):
    if call.message:
        if call.data == "button1":
            bot.send_message(call.message.chat.id, "Напиши команду /anek, /bird или /But и посмотри что будет", reply_markup=get_keyboard())
        if call.data == "button2":
            bot.send_message(call.message.chat.id, "/anek", reply_markup=get_keyboard())
        if call.data == "button3":
            bot.send_message(call.message.chat.id, "/Set", reply_markup=get_keyboard())
        if call.data == "button4":
            bot.send_message(call.message.chat.id, "/bird", reply_markup=get_keyboard())



# content_types=['text'] - сработает, если нам прислали текстовое сообщение
@bot.message_handler(commands=['bird'])
def echo(message):
    # message - входящее сообщение
    # message.text - это его текст
    # message.chat.id - это номер его автора
    text = "Азазазаазазазазаазаазазаазазазазазаазазаазазаазазаазаазазаазазаазазазазаззазааза"
    user = message.chat.id

    #отправляем сообщение тому же пользователю с тем же текстом
    bot.send_message(user, text, reply_markup=get_keyboard())


    

# поллинг - вечный цикл с обновлением входящих сообщений
bot.polling(none_stop=True)

