#!/bin/bash

secret=$((RANDOM % 100 + 1))
guess=0
attempts=0

echo "Я загадал число от 1 до 100. Попробуй угадать!"

while [ $guess -ne $secret ]; do
    read -p "Твой вариант: " guess
    ((attempts++))

    if [ $guess -lt $secret ]; then
        echo "Бери выше!"
    elif [ $guess -gt $secret ]; then
        echo "Бери ниже!"
    else
        echo "Красавчик! Угадал с $attempts попытки 🎉"
    fi
done
