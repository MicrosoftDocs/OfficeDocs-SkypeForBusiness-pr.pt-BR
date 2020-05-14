---
title: Gerenciar definições de configuração de serviço de registro em log centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221171"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gerenciar definições de configuração de serviço de registro em log centralizado no Skype for Business Server 2015

**Resumo:** Saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype for Business Server 2015.

O serviço de registro em log centralizado é controlado e configurado por configurações e parâmetros que são criados e usados pelo CLSController (controlador de serviço de registro em log centralizado) para enviar comandos ao agente de serviço de registro em log centralizado do computador individual (CLSAgent). O agente processa os comandos que são enviados a ele e (no caso de um comando Start) usa a configuração dos cenários, provedores, duração do rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.

> [!IMPORTANT]
>  Nem todos os cmdlets do Windows PowerShell listados para o serviço de registro em log centralizado devem ser usados com as implantações locais do Skype for Business Server 2015. Embora eles possam parecer funcionar, os cmdlets a seguir não foram projetados para funcionar com as implantações locais do Skype for Business Server 2015:

-  **Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

As configurações definidas nesses cmdlets não afetarão nem causarão qualquer comportamento adverso, mas serão projetadas para uso com o Microsoft 365 ou o Office 365 e não produzirão os resultados esperados em implantações locais. Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado que não é abordado nesta documentação.

O serviço de registro em log centralizado pode ser executado em um escopo que inclui um único computador ou um pool de computadores, em um escopo de site (ou seja, um site definido como o site Redmond que contém uma coleção de computador e pools em sua implantação) ou em um escopo global (ou seja, todos os computadores e pools em sua implantação).

Para configurar o escopo de serviço de registro em log centralizado usando o Shell de gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança do controle de acesso baseado em função do CsAdministrator ou do CsServerAdministrator, ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no Shell de gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Por exemplo:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Há diferenças fundamentais entre os comandos de linha de comando que podem ser executados no Windows PowerShell ou no CLSController. O Windows PowerShell oferece um método avançado para configurar e definir cenários, e para reutilizar esses cenários de uma maneira significativa para seus cenários de solução de problemas. Embora o CLSController does forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando. Diferentemente dos cmdlets do Windows PowerShell, o CLSController não pode definir novos cenários, gerenciar o escopo em um nível global ou de site, e muitas outras limitações de um conjunto de comandos finito que não pode ser configurado dinamicamente. Embora o CLSController forneça um meio de execução rápida, o Windows PowerShell oferece meios para estender a funcionalidade de serviço de registro centralizado além do que é possível com o CLSController.

Um único escopo de computador pode ser definido durante a execução de um comando [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) usando o parâmetro-Computers. O parâmetro-Computers aceita uma lista separada por vírgulas de FQDNs (nomes de domínio totalmente qualificados) para o computador de destino.

> [!TIP]
> Você também pode definir pools e uma lista separada por vírgulas de pools nos quais você deseja executar os comandos de log.

Os escopos de site e globais são definidos nos cmdlets do serviço de registro em log **New-**, **set-** e **Remove-** centralizado. Os exemplos a seguir demonstram como definir o escopo de um site ou global.

> [!IMPORTANT]
> Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções. Os comandos de exemplo se destinam a demonstrar o uso do parâmetro **-Identity** para definir o escopo, e os outros parâmetros são incluídos para integridade e para especificar o escopo. Para obter detalhes sobre os cmdlets do **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) na documentação Operações.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar a configuração atual do serviço de registro em log centralizado

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Use os cmdlets **New-CsClsConfiguration** e **set-CsClsConfiguration** para criar uma nova configuração ou para atualizar uma configuração existente. Quando você executa o **Get-CsClsConfiguration**, ele exibe informações semelhantes à captura de tela a seguir, onde a implantação atualmente tem a configuração global padrão, mas nenhuma configuração de site definida:

![Exemplo de saída de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar a configuração do serviço de registro em log centralizado atual do repositório local do computador

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Quando você usa o primeiro exemplo em que **Get-CsClsConfiguration** não especifica nenhum parâmetro, o comando faz referência ao repositório de gerenciamento central dos dados. Se você especificar o parâmetro-LocalStore, o comando faz referência ao computador LocalStore em vez do repositório de gerenciamento central.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar uma lista de cenários definidos no momento

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Por exemplo, para recuperar os cenários definidos no escopo global:

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte de uma determinada configuração de escopo. Na maioria dos casos, nem todos os cenários são exibidos e estão truncados. O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo global para o serviço de registro em log centralizado usando o Windows PowerShell

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Por exemplo:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo de site para o serviço de registro em log centralizado usando o Windows PowerShell

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para criar uma nova configuração de serviço de registro em log centralizado

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais. Para obter detalhes sobre as opções de configuração, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [Understanding central Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Você deve planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o serviço de registro em log centralizado. Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente. Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para remover uma configuração de serviço de registro em log centralizado existente

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.

2. Digite o seguinte no prompt de linha de comando:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Por exemplo, para remover uma configuração de serviço de registro em log centralizado que você criou para aumentar o tempo de substituição do arquivo de log, aumente o tamanho do arquivo de log de substituição e defina o local do cache do arquivo de log para um compartilhamento de rede da seguinte maneira:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Esta é a nova configuração que foi criada no procedimento "para criar uma nova configuração de serviço de registro em log centralizado".

Se decidir remover a configuração no nível do site, o site usará as configurações globais.
## <a name="see-also"></a>Confira também

[Configurar provedores para o serviço de registro em log centralizado no Skype for Business Server 2015](configure-providers.md)

[Configurar cenários para o serviço de registro em log centralizado no Skype for Business Server 2015](configure-scenarios.md)

[Serviço de registro em log centralizado no Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
