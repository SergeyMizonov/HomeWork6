Задача 41: Пользователь вводит с клавиатуры M чисел. 
Посчитайте, сколько чисел строго больше 0 ввёл пользователь.
Console.Write("Введите числа через пробел: ");
int[] numbers = GetArrayFromString(Console.ReadLine()!);
Console.WriteLine($"Количество чисел больше 0 -> {GetCountPositiveElements(numbers)}");


int[] GetArrayFromString(string stringArray)
{
          string[] numS = stringArray.Split(' ', StringSplitOptions.RemoveEmptyEntries);
          int[] result = new int[numS.Length];
          for (int i = 0; i < result.Length; i++)
          {
                    result[i] = int.Parse(numS[i]);
          }
          return result;
}

int GetCountPositiveElements(int [] array)
{
          int count = 0;
          foreach (var item in array)
          {
                    if (item > 0) count++;
          }
          return count;
}


Задача 43: Написать программу, которая на вход принимает массив из любого 
количества элементов (не менее 6)в промежутке от 0 до 100, 
а на выходе выводит этот же массив, но отсортированный по возрастанию
(от меньшего числа к большему).
int[] array = CreateArray(6);
Console.WriteLine($"[{String.Join(" , ", array)}]");
SortArray(array);
Console.WriteLine($"[{String.Join(" , ", array)}]");
int[] CreateArray (int size)
{
          int[] array = new int[size];
          for (int i = 0; i < array.Length; i++)
          {
                    array[i] = new Random().Next(0, 100);
          }
          return array;
}
void SortArray(int[] array)
{
          for (int i = 0; i < array.Length - 1; i++)
          {
                    for (int j = i + 1; j < array.Length; j++)
                    {
                              if (array[i] > array[j])
                              {
                                        int temp = array[i];
                                        array[i] = array[j];
                                        array[j] = temp;

                              }
                    }
          }
}


