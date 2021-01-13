---
title: Gerenciar definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumo: Saiba como recuperar, atualizar e criar definições de configuração para o Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835151"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gerenciar definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015

**Resumo:** Saiba como recuperar, atualizar e criar definições de configuração para o Serviço de Log Centralizado no Skype for Business Server 2015.

O Serviço de Registro em Log Centralizado é controlado e configurado por configurações e parâmetros criados e usados pelo Controlador de Serviço de Log Centralizado (CLSController) para enviar comandos ao Agente de Serviço de Log Centralizado (CLSAgent) do computador individual. O agente processa os comandos que são enviados a ele e (no caso de um comando Iniciar) usa a configuração dos cenários, provedores, duração de rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.

> [!IMPORTANT]
>  Nem todos os cmdlets do Windows PowerShell listados para o Serviço de Log Centralizado se destinam ao uso com implantações locais do Skype for Business Server 2015. Embora possam parecer funcionar, os seguintes cmdlets não foram projetados para funcionar com implantações locais do Skype for Business Server 2015:

-  **Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

As configurações definidas nesses cmdlets não impedirão ou causarão nenhum comportamento adverso, mas elas foram projetadas para uso com o Microsoft 365 ou o Office 365 e não gerarão os resultados esperados em implantações locais. Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado que não é abordado nesta documentação.

O Serviço de Log Centralizado pode ser executado em um escopo que inclui um único computador ou pool de computadores, em escopo de site (ou seja, um site definido, como o site Redmond que contém uma coleção de computadores e pools em sua implantação) ou em um escopo global (ou seja, todos os computadores e pools em sua implantação).

Para configurar o escopo do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções do RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você mesmo tenha criado), execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por exemplo:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Há diferenças fundamentais entre os comandos de linha de comando que você pode executar no Windows PowerShell ou CLSController. O Windows PowerShell fornece um método rico para configurar e definir cenários e reutilizar esses cenários de maneira significativa para seus cenários de solução de problemas. Embora o CLSController does forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando. Ao contrário dos cmdlets do Windows PowerShell, o CLSController não pode definir novos cenários, gerenciar o escopo em um nível de site ou global e muitas outras limitações de um conjunto de comandos finito que não pode ser configurado dinamicamente. Embora o CLSController fornece um meio para execução rápida, o Windows PowerShell fornece um meio para estender a funcionalidade do Serviço de Log Centralizado além do que é possível com o CLSController.

Um escopo de computador único pode ser definido durante a execução de um [comando Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) usando o parâmetro -Computers. O parâmetro -Computers aceita uma lista separada por vírgulas de FQDNs (nomes de domínio totalmente qualificados) para o computador de destino.

> [!TIP]
> Também é possível definir -Pools e uma lista separada por vírgulas de pools nos quais você deseja executar os comandos de log.

Os escopos de Site e Global são definidos nos cmdlets **New-**, **Set-** e **Remove-** Centralized Logging Service. Os exemplos a seguir demonstram como definir o escopo de um site ou global.

> [!IMPORTANT]
> Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções. Os comandos de exemplo destinam-se a demonstrar o uso do parâmetro **-Identity** para definir o escopo, e os outros parâmetros são incluídos para a abrangência completa e para especificar o escopo. Para obter detalhes sobre os cmdlets do **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) na documentação Operações.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar a configuração atual do Serviço de Log Centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou atualizar uma configuração existente. Quando você executar **Get-CsClsConfiguration,** ele exibirá informações semelhantes à captura de tela a seguir, em que a implantação tem a configuração global padrão, mas nenhuma configuração de site definida:

![Exemplo de saída de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar a configuração atual do Serviço de Log Centralizado do armazenamento local do computador

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Quando você usa o primeiro exemplo em que **Get-CsClsConfiguration** não especifica nenhum parâmetro, o comando faz referência ao armazenamento de Gerenciamento Central para os dados. Se você especificar o parâmetro -LocalStore, o comando referencia o LocalStore do computador em vez do repositório de Gerenciamento Central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar uma lista de cenários definidos no momento

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Por exemplo, para recuperar os cenários definidos no escopo global:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte da configuração de um determinado escopo. Na maioria dos casos, nem todos os cenários são exibidos e estão truncados. O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo global para o Serviço de Log Centralizado usando o Windows PowerShell

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por exemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo de site para o Serviço de Log Centralizado usando o Windows PowerShell

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por exemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para criar uma nova configuração do Serviço de Log Centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais. Para obter detalhes sobre as opções de configuração, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Você deve planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o Serviço de Log Centralizado. Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente. Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para remover uma configuração existente do Serviço de Log Centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Por exemplo, para remover uma configuração do Serviço de Log Centralizado que você criou para aumentar o tempo de sobremoção do arquivo de log, aumente o tamanho do arquivo de log de sobremoção e de definir o local do cache do arquivo de log para um compartilhamento de rede da seguinte forma:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta é a nova configuração criada no procedimento "Para criar uma nova configuração do Serviço de Log Centralizado".

Se decidir remover a configuração no nível do site, o site usará as configurações globais.
## <a name="see-also"></a>Confira também

[Configurar provedores para o Serviço de Log Centralizado no Skype for Business Server 2015](configure-providers.md)

[Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
