# Alive1exekusra41
2 sem. 1 kursa4
Терех Владислав
Тема: Клавиатурный тренажёр.


код:
#include <iostream>
#include <string>
#include <windows.h>
#include <cstring>

using namespace std;


int main()
{
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);

	bool MainMenuResult = true;
	while (MainMenuResult == true)
	{
		int MainMenuChoice;
		cout << " ////////////////////////////////////////////////////////////////////////";
		cout << "\n     Приветствуем вас в Development-версии клавиатурного тренажёра!";
		cout << "\n ////////////////////////////////////////////////////////////////////////";
		cout << "\n \n Hint: Используйте клавиатуру для ввода и подтвеержения выбора.";
		cout << "\n \n ------------------------------------------------------------------------";
		cout << "\n \n 1. Запустить клавиатурный тренажёр";
		cout << "\n 2. Выйти из программы";
		cin >> MainMenuChoice;
		if (MainMenuChoice == 1) {
			//clear
			int TrainingMenuChoice;
			cout << "\n ////////////////////////////////////////////////////////////////////////";
			cout << "\n     Вы в шаге от начала тренировки.";
			cout << "\n     ------------------------------------------------------------------------";
			cout << "\n     На данный момент программа содержит один текст.";
			cout << "\n     ------------------------------------------------------------------------";
			cout << "\n     Тренировка происходит в следующем формате:";
			cout << "\n     Вы видите на экране текст, который необходимо ввести с клавиатуры.";
			cout << "\n     Вводить можно абсолютно любое количество символов любого характера.";
			cout << "\n     ------------------------------------------------------------------------";
			cout << "\n \n     Один неправильно введённый символ - одна ошибка: -10 очков.";
			cout << "\n     Один правильно введённый символ: +10 очков.";
			cout << "\n \n ////////////////////////////////////////////////////////////////////////";
			cout << "\n \n      Подтвердите готовность: ";
			cout << "\n \n      1. Готов! ";
			cout << "\n      2. Уведите меня отсюда! А дальше я сам!     (В главное меню)";
			cin >> TrainingMenuChoice;
			if (TrainingMenuChoice == 1) {
				//clear
				string TextOriginal = "aaa bbb";
				string TextUser = "";
				//std::string TextOriginal = "111 aaa bbb";
				//std::string TextUser;
				cout << "\n ////////////////////////////////////////////////////////////////////////";
				cout << "\n Текст для ввода: "<< TextOriginal;
				cout << "\n ------------------------------------------------------------------------";
				cout << "\n \n Ваш текст: ";
				//cin.getline(TextUser, 257);
				//while (cin >> TextUser) 
				//{
				//}
				cin >> TextUser;
				//std::getline(std::cin, TextUser);
				cout << "\n ------------------------------------------------------------------------";
				cout << "\n ------------------------------------------------------------------------";
				cout << TextUser;
				cout << "\n ------------------------------------------------------------------------";
				cout << TextOriginal;
				cout << "\n ------------------------------------------------------------------------";
				cout << "\n ------------------------------------------------------------------------";
				
				int RightSymbols = 0;
				int Mistakes = 0;
				int Score = 0;
				bool GetScore = false;
				while (GetScore == false) {
					for (int i = 0; i < 11; i++) {
						if (TextOriginal[i] == TextUser[i]) {
							Score = Score + 10;
							RightSymbols = RightSymbols + 1;
						}
						else if (TextOriginal[i] != TextUser[i]) {
							Score = Score - 10;
							Mistakes = Mistakes + 1;
						}
						else {
							cout << "Error getting score on" << i << "symbol";
						}					
					}
					GetScore = true;					
				}
				//clear
				cout << "\n ////////////////////////////////////////////////////////////////////////";
				cout << "\n     Поздравляем! ";
				cout << "\n     ------------------------------------------------------------------------";
				cout << "\n     Вы набрали: " << Score << " очков";
				cout << "\n     Вы сделали: " << Mistakes << " ошибок";
				cout << "\n     Правильно введено: " << RightSymbols << " символов";
				cout << "\n     ------------------------------------------------------------------------";
				cout << "\n     После продолжения вы будете возвращены в главное меню.";
				cout << "\n ////////////////////////////////////////////////////////////////////////";
				system("pause");

				
			}
			else if (TrainingMenuChoice == 2) {
				//clear
				cout << "\n \n ------------------------------------------------------------------------";
				cout << "\n      Вы будете возвращены в главное меню";
				cout << "\n \n ------------------------------------------------------------------------";
				system("pause");
			}
			else
			{
				//clear
				cout << "\n \n ------------------------------------------------------------------------";
				cout << "\n      !Warning! Неправильный выбор.";
				cout << "\n \n ------------------------------------------------------------------------";
				system("pause");
			}





		}
		else if (MainMenuChoice == 2) {
			MainMenuResult = false;
			//clear
			cout << "\n \n ------------------------------------------------------------------------";
			cout << "\n      Был произведён выход из программы. Всего доброго!";
			cout << "\n \n ------------------------------------------------------------------------";
		}
		else
		{
			//clear
			cout << "\n \n ------------------------------------------------------------------------";
			cout << "\n      !Warning! Неправильный выбор.";
			cout << "\n \n ------------------------------------------------------------------------";
			system("pause");
		}
	}
	system("pause");
	return 0;
}
