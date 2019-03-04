---
title: Beispiel für StopProcessSample04 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac4903f5-fd40-4f1c-b1d1-18923c16ce45
caps.latest.revision: 8
ms.openlocfilehash: 63f04e4caebc31974f35b49309b176241c9b8d4b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860536"
---
# <a name="stopprocesssample04-sample"></a><span data-ttu-id="253a7-102">StopProcessSample04-Beispiel</span><span class="sxs-lookup"><span data-stu-id="253a7-102">StopProcessSample04 Sample</span></span>

<span data-ttu-id="253a7-103">Dieses Beispiel zeigt, wie ein Cmdlet, das deklariert Parameter legt fest, gibt an, die Standardparameter festgelegt, und ein Eingabeobjekt akzeptieren geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="253a7-103">This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span> <span data-ttu-id="253a7-104">Dieses Cmdlet ähnelt dem `Stop-Process` Cmdlet von Windows PowerShell 2.0 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="253a7-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="253a7-105">So erstellen Sie das Beispiel mithilfe von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="253a7-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="253a7-106">Navigieren Sie zum Ordner StopProcessSample04, mit dem Windows PowerShell 2.0 SDK installiert.</span><span class="sxs-lookup"><span data-stu-id="253a7-106">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample04 folder.</span></span> <span data-ttu-id="253a7-107">Der standardmäßige Speicherort ist C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="253a7-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample04.</span></span>

2. <span data-ttu-id="253a7-108">Doppelklicken Sie auf das Symbol für die Projektmappendatei (.sln).</span><span class="sxs-lookup"><span data-stu-id="253a7-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="253a7-109">Daraufhin wird das Beispielprojekt in Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="253a7-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="253a7-110">In der **erstellen** , wählen Sie im Menü **Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="253a7-110">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="253a7-111">Die Bibliothek für das Beispiel wird in die Standardordner \bin oder \bin\debug erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="253a7-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="253a7-112">Gewusst wie: Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="253a7-112">How to run the sample</span></span>

1. <span data-ttu-id="253a7-113">Erstellen Sie die folgenden Ordner "Module":</span><span class="sxs-lookup"><span data-stu-id="253a7-113">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample04`

2. <span data-ttu-id="253a7-114">Kopieren Sie die Beispielassembly, auf den Ordner "Module".</span><span class="sxs-lookup"><span data-stu-id="253a7-114">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="253a7-115">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="253a7-115">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="253a7-116">Führen Sie den folgenden Befehl zum Laden der Assembly in Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="253a7-116">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample04`

5. <span data-ttu-id="253a7-117">Führen Sie den folgenden Befehl das Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="253a7-117">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="253a7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="253a7-118">Requirements</span></span>

<span data-ttu-id="253a7-119">Dieses Beispiel ist die Windows PowerShell 2.0 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="253a7-119">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="253a7-120">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="253a7-120">Demonstrates</span></span>

<span data-ttu-id="253a7-121">Dieses Beispiel veranschaulicht die folgenden.</span><span class="sxs-lookup"><span data-stu-id="253a7-121">This sample demonstrates the following.</span></span>

- <span data-ttu-id="253a7-122">Deklarieren Sie eine Cmdlet-Klasse, mit dem Cmdlet-Attribut.</span><span class="sxs-lookup"><span data-stu-id="253a7-122">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="253a7-123">Deklarieren ein Cmdlet-Parameter mit dem Parameter-Attribut.</span><span class="sxs-lookup"><span data-stu-id="253a7-123">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="253a7-124">Hinzufügen eines Parameters, der das input-Objekt annimmt.</span><span class="sxs-lookup"><span data-stu-id="253a7-124">Adding a parameter that accepts input object.</span></span>

- <span data-ttu-id="253a7-125">Hinzufügen von Parametern zur Parametersätze</span><span class="sxs-lookup"><span data-stu-id="253a7-125">Adding parameters to parameter sets</span></span>

- <span data-ttu-id="253a7-126">Legen Sie den Standardparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="253a7-126">Specifying the default parameter set.</span></span>

## <a name="example"></a><span data-ttu-id="253a7-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="253a7-127">Example</span></span>

<span data-ttu-id="253a7-128">Der folgende Code zeigt eine Implementierung von das Stop-Proc-Cmdlet, das Deklarieren von Parametersätzen, gibt an, die Standardparameter festgelegt, und ein Eingabeobjekt akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="253a7-128">The following code shows an implementation of the Stop-Proc cmdlet that declare parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="253a7-129">Dieses Beispiel zeigt das Eingabeobjekt, wie Parametersätze deklariert und wie an den Standard-Parametersatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="253a7-129">This sample shows the input object, how to declare parameter sets, and how to specify the default parameter set to use.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;             //Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

   /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       DefaultParameterSetName = "ProcessId",
       SupportsShouldProcess = true)]
   public class StopProcCommand : PSCmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          ParameterSetName = "ProcessName",
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true,
          HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
       )]
       [Alias("ProcessName")]
       public string[] Name
       {
           get { return processNames; }
           set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter(
          HelpMessage = "If set the process(es) will be passed to the pipeline after stopped."
       )]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

      /// This parameter provides the list of process identifiers on
      /// which the Stop-Proc cmdlet will work.
       [Parameter(
          ParameterSetName = "ProcessId",
          Mandatory = true,
          ValueFromPipelineByPropertyName = true,
          ValueFromPipeline = true
       )]
       [Alias("ProcessId")]
       public int[] Id
       {
           get { return processIds; }
           set { processIds = value; }
       }
       private int[] processIds;

       /// <summary>
       /// This parameter accepts an array of Process objects from the
       /// the pipeline. This object contains the processes to stop.
       /// </summary>
       /// <value>Process objects</value>
       [Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
       public Process[] InputObject
       {
           get { return inputObject; }
           set { inputObject = value; }
       }
       private Process[] inputObject;

       #endregion Parameters

       #region CmdletOverrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           switch (ParameterSetName)
           {
               case "ProcessName":
                   ProcessByName();
               break;

               case "ProcessId":
                   ProcessById();
                   break;

               case "InputObject":
                   foreach (Process process in inputObject)
                   {
                       SafeStopProcess(process);
                   }
                   break;

               default:
                   throw new ArgumentException("Bad ParameterSet Name");
           } // switch (ParameterSetName...
       } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Helper Methods

       /// <summary>
       /// Returns all processes with matching names.
       /// </summary>
       /// <param name="processName">
       /// The name of the processes to return.
       /// </param>
       /// <param name="allProcesses">An array of all
       /// computer processes.</param>
       /// <returns>An array of matching processes.</returns>
       internal ArrayList SafeGetProcessesByName(string processName,
                                ref ArrayList allProcesses)
       {
           // Create and array to store the matching processes.
           ArrayList matchingProcesses = new ArrayList();

           // Create the wildcard for pattern matching.
           WildcardOptions options = WildcardOptions.IgnoreCase |
                                     WildcardOptions.Compiled;
           WildcardPattern wildcard = new WildcardPattern(processName, options);

           // Walk all of the machine processes.
           foreach(Process process in allProcesses)
           {
               string processNameToMatch = null;
               try
               {
                   processNameToMatch = process.ProcessName;
               }
               catch (Win32Exception e)
               {
                   // Remove the process from the list so that it is not
                   // checked again.
                   allProcesses.Remove(process);

                   string message =
                         String.Format(CultureInfo.CurrentCulture, "The process \"{0}\" could not be found",
                                             processName);
                   WriteVerbose(message);
                   WriteError(new ErrorRecord(e, "ProcessNotFound",
                                    ErrorCategory.ObjectNotFound, processName));

                   continue;
               }

               if (!wildcard.IsMatch(processNameToMatch))
               {
                   continue;
               }

               matchingProcesses.Add(process);
           } // foreach(Process...

           return matchingProcesses;
       } // SafeGetProcessesByName

       /// <summary>
       /// Safely stops a named process.  Used as standalone function
       /// to declutter the ProcessRecord method.
       /// </summary>
       /// <param name="process">The process to stop.</param>
       private void SafeStopProcess(Process process)
       {
           string processName = null;

           try
           {
               processName = process.ProcessName;
           }
           catch (Win32Exception e)
           {
               WriteError(new ErrorRecord(e, "ProcessNotFound",
                                ErrorCategory.OpenError, processName));

               return;
           }

           // Confirm the operation first.
           // This is always false if the WhatIf parameter is specified.
           if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,
                    "{0} ({1})", processName, process.Id)))
           {
               return;
           }

           // Make sure that the user really wants to stop a critical
           // process that can possibly stop the computer.
           bool criticalProcess = criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

           string message = null;
           if (criticalProcess && !force)
           {
               message = String.Format(CultureInfo.CurrentCulture,
                                            "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                                processName);
               // It is possible that the ProcessRecord method is called
               // multiple times when objects are recieved as inputs from
               // the pipeline. So to retain YesToAll and NoToAll input that
               // the user may enter across mutilple calls to this function,
               // they are stored as private members of the cmdlet.
               if (!ShouldContinue(message, "Warning!",
                            ref yesToAll, ref noToAll))
               {
                   return;
               }
           } // if (criticalProcess...

           // Display a warning message if stopping a critical
           // process.
           if (criticalProcess)
           {
               message =
                 String.Format(CultureInfo.CurrentCulture,
                                "Stopping the critical process \"{0}\".",
                                    processName);
               WriteWarning(message);
           } // if (criticalProcess...

           try
           {
               // Stop the process.
               process.Kill();
           }
           catch (Exception e)
           {
               if ((e is Win32Exception) || (e is SystemException) ||
                   (e is InvalidOperationException))
               {
                   // This process could not be stopped so write
                   // a non-terminating error.
                   WriteError(new ErrorRecord(e, "CouldNotStopProcess",
                                    ErrorCategory.CloseError,
                                    process)
                              );

                   return;
               } // if ((e is...
               else throw;
           } // catch

           // Write a user-level verbose message to the pipeline. These are
           // intended to give the user detailed information on the
           // operations performed by the cmdlet. These messages will
           // appear with the -Verbose option.
           message = String.Format(CultureInfo.CurrentCulture,
                                        "Stopped process \"{0}\", pid {1}.",
                                            processName, process.Id);

           WriteVerbose(message);

           // If the PassThru prameter is specified, return the terminated
           // process to the pipeline.
           if (passThru)
           {
               // Write a debug message to the host that can be used
               // when troubleshooting a problem. All debug messages
               // will appear with the -Debug option
               message =
                   String.Format(CultureInfo.CurrentCulture,
                                    "Writing process \"{0}\" to pipeline",
                                        processName);
               WriteDebug(message);
               WriteObject(process);
           } // if (passThru..
       } // SafeStopProcess

       /// <summary>
       /// Stop processes based on their names (using the
       /// ParameterSetName as ProcessName)
       /// </summary>
       private void ProcessByName()
       {
           ArrayList allProcesses = null;

           // Get a list of all processes.
           try
           {
               allProcesses = new ArrayList(Process.GetProcesses());
           }
           catch (InvalidOperationException ioe)
           {
               base.ThrowTerminatingError(new ErrorRecord(
                    ioe, "UnableToAccessProcessList",
                    ErrorCategory.InvalidOperation, null));
           }

           // If a process name is passed to the cmdlet, get
           // the associated processes.
           // Write a nonterminating error for failure to
           // retrieve a process.
           foreach (string name in processNames)
           {
               // The allProcesses array list is passed as a reference because
               // any process whose name cannot be obtained will be removed
               // from the list so that its not compared the next time.
               ArrayList processes =
                   SafeGetProcessesByName(name, ref allProcesses);

               // If no processes were found write a non-
               // terminating error.
               if (processes.Count == 0)
               {
                   WriteError(new ErrorRecord(
                       new Exception("Process not found."),
                       "ProcessNotFound",
                       ErrorCategory.ObjectNotFound,
                       name));
               } // if (processes...
               // Otherwise terminate all processes in the list.
               else
               {
                   foreach (Process process in processes)
                   {
                       SafeStopProcess(process);
                   } // foreach (Process...
               } // else
           } // foreach (string...
       } // ProcessByName

       /// <summary>
       /// Stop processes based on their identifiers (using the
       /// ParameterSetName as ProcessIds)
       /// </summary>
       internal void ProcessById()
       {
           foreach (int processId in processIds)
           {
               Process process = null;
               try
               {
                   process = Process.GetProcessById(processId);

                   // Write a debug message to the host that can be used
                   // when troubleshooting a problem. All debug messages
                   // will appear with the -Debug option
                   string message =
                       String.Format(CultureInfo.CurrentCulture,
                                        "Acquired process for pid : {0}",
                                            process.Id);
                   WriteDebug(message);
               }
               catch (ArgumentException ae)
               {
                   string
                       message = String.Format(CultureInfo.CurrentCulture,
                                            "The process id {0} could not be found",
                                                processId);
                   WriteVerbose(message);
                   WriteError(new ErrorRecord(ae, "ProcessIdNotFound",
                                    ErrorCategory.ObjectNotFound, processId));
                   continue;
               }

               SafeStopProcess(process);
           } // foreach (int...
       } // ProcessById

       #endregion Helper Methods

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv", "calc" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="253a7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="253a7-130">See Also</span></span>

[<span data-ttu-id="253a7-131">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="253a7-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)