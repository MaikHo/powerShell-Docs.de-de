---
title: Schreiben eines einfachen Cmdlets | Microsoft-Dokumentation
ms.date: 01/15/2019
ms.openlocfilehash: 2ff0b47454804c9becd6f03ac521946b9596bb8b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784060"
---
# <a name="how-to-write-a-cmdlet"></a>Schreiben eines Cmdlets

In diesem Artikel wird gezeigt, wie Sie ein Cmdlet schreiben. Das `Send-Greeting` Cmdlet nimmt einen einzelnen Benutzernamen als Eingabe an und schreibt dann eine Begrüßung an diesen Benutzer. Obwohl das Cmdlet nicht viel Arbeit leistet, veranschaulicht dieses Beispiel die Hauptabschnitte eines Cmdlets.

## <a name="steps-to-write-a-cmdlet"></a>Schritte zum Schreiben eines Cmdlets

1. Verwenden Sie das **Cmdlet** -Attribut, um die Klasse als Cmdlet zu deklarieren. Das **Cmdlet** -Attribut gibt das Verb und das Substantiv für den Namen des Cmdlets an.

   Weitere Informationen zum **Cmdlet** -Attribut finden Sie unter [CmdletAttribute-Deklaration](cmdlet-attribute-declaration.md).

2. Geben Sie den Namen der Klasse an.

3. Legen Sie fest, dass das Cmdlet von einer der folgenden Klassen abgeleitet ist:

   * [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)
   * [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

4. Um die Parameter für das Cmdlet zu definieren, verwenden Sie das **Parameter** Attribut. In diesem Fall wird nur ein erforderlicher Parameter angegeben.

   Weitere Informationen zum **Parameter** -Attribut finden Sie unter [Parameterattribute-Deklaration](parameter-attribute-declaration.md).

5. Überschreiben Sie die Eingabe Verarbeitungsmethode, die die Eingabe verarbeitet. In diesem Fall wird die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode überschrieben.

6. Um die Begrüßung zu schreiben, verwenden Sie die Methode [System. Management. Automation. Cmdlet. Write-Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).
   Die Begrüßung wird im folgenden Format angezeigt:

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a>Beispiel

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)

[System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. Cmdlet. Write Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[CmdletAttribute-Deklaration](cmdlet-attribute-declaration.md)

[ParameterAttribute-Deklaration](parameter-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](writing-a-windows-powershell-cmdlet.md)
