---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_PrintJob_v1.0.cdxml-help.xml
Module Name: PrintManagement
ms.date: 9/20/2021
online version: https://docs.microsoft.com/powershell/module/printmanagement/resume-printjob?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-PrintJob
---

# Resume-PrintJob

## SYNOPSIS
Resumes a suspended print job.

## SYNTAX

### jobObject
```
Resume-PrintJob [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### printerName
```
Resume-PrintJob [-ComputerName <String>] [-ID] <UInt32> [-PrinterName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### printer_object
```
Resume-PrintJob [-ID] <UInt32> [-PrinterObject] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-PrintJob** cmdlet resumes a suspended print job on the specified printer.
The **Resume-PrintJob** cmdlet has no effect if any print job is running.

You can specify the print job to resume by specifying the *PrinterName* and *ID* parameters, by specifying the printer object and job *ID* parameter, or by specifying the print job object as an input.

You cannot use wildcard characters with **Resume-PrintJob**.

## EXAMPLES

### Example 1: Resume a suspended print job
```
Resume-PrintJob - PrinterName "PrinterName" -ID 1
```

This command resumes the print job with an ID of 1, which was suspended on the printer named PrinterName.

### Example 2: Resume a print job using a printer object and job ID
```
$Printer = Get-Printer -PrinterName "PrinterName"
Resume-PrintJob -PrinterObject $Printer -ID 1
```

The first command gets a printer named PrinterName by using the Get-Printer cmdlet.
The command stores the result in the $Printer variable.

The second command resumes the print job that has the ID 1 on the printer in $Printer.

### Example 3: Resume a print job using a job object
```
$PrintJob = Get-PrintJob - PrinterName "PrinterName" -ID 1
Resume-PrintJob -InputObject $PrintJob
```

The first command gets a printer job that has the ID on a printer named PrinterName by using the Get-PrintJob cmdlet.
The command stores the result in the $PrintJob variable.

The second command resumes the print job in $PrintJob.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which to resume the print job.

```yaml
Type: String
Parameter Sets: printerName
Aliases: CN, computer

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the ID of the print job to resume on the specified printer.
You can use wildcard characters.

```yaml
Type: UInt32
Parameter Sets: printerName, printer_object
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: jobObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrinterName
Specifies the name of the printer on which to resume the print job.

```yaml
Type: String
Parameter Sets: printerName
Aliases: PN

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrinterObject
Specifies the object which contains the printer on which to resume the print job.

```yaml
Type: CimInstance
Parameter Sets: printer_object
Aliases: Printer

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

### System.String

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-PrintJob](./Get-PrintJob.md)

[Remove-PrintJob](./Remove-PrintJob.md)

[Restart-PrintJob](./Restart-PrintJob.md)

[Suspend-PrintJob](./Suspend-PrintJob.md)

