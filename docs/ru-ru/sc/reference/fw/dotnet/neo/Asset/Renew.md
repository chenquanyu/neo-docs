# Asset.Renew Method (byte[])

Для продления актива.

Данный метод является новым для версии 2.0. После регистрации активов необходимо заплатить годовую комиссию, иначе они будут заморожены.

Когда срок действия актива истекает, необходимо его продлить. Если актив не заморожен, комиссия за продление продлит срок его действия, отталкиваясь от даты истечения срока. Если актив заморожен, комиссия за продление продлит срок его действия, начиная с момента оплаты комиссии. Таким образом, задолженность будет невозможна после оплаты комиссии за продление.

Namespace: [Neo.SmartContract.Framework.Services.Neo](../../neo.md)

Assembly: Neo.SmartContract.Framework

## Syntax

```c#
public extern uint Renew (byte years)
```

Параметры: Период обновления (один год равен 2 000 000 блоков, байтовый тип).

Возвращаемое значение: Высота блока, где актив может быть использован до, после обновления.

## Пример

```c#
public class Contract1: FunctionCode
{
    public static void Main()
    {
        // Taking NEO shares as an example
        byte[] asset = {197, 111, 51, 252, 110, 207, 205, 12, 34, 92, 74, 179, 86, 254, 229, 147, 144, 175, 133, 96, 190, 147, 15, 174, 190, 116, 166, 218, 255, 124, 155};
        Asset ass = Blockchain.GetAsset(asset);
        uint blockIndex = ass.Renew (1);
    }
}
```



[Back](../Asset.md)
