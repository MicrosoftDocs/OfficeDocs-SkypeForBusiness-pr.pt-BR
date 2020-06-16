---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789a8a83c8f3ee831fb91c85999d936ea54dd8b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

A migração do aplicativo de estacionamento de chamada do Lync Server 2010 para o Lync Server 2013 inclui o provisionamento do pool do Lync Server 2013 com qualquer música personalizada em arquivos de espera que foram carregados no Lync Server 2010, restaurando as configurações de nível de serviço e redirecionando todas as órbitas de estacionamento de chamadas para o pool do Lync Server 2013. Se os arquivos de música em espera personalizados tiverem sido configurados no pool do Lync Server 2010, esses arquivos precisam ser copiados para o novo pool do Lync Server 2013. Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera personalizados de um estacionamento de chamadas do Lync Server 2010 para outro destino, para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para estacionamento de chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos do pool do Lync Server 2010 para um repositório de arquivos do Lync Server 2013, use o comando **xcopy** com os seguintes parâmetros:

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Lync Server 2013, as configurações de aplicativo de estacionamento de chamada do pool do Lync Server 2013 devem ser configuradas, e os intervalos de órbita de estacionamento de chamada associados ao pool 2010 do Lync Server devem ser reatribuídos ao pool do Lync Server 2013.

As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de recebimento, habilitando ou desabilitando música em espera, o máximo de tentativas de recebimento de chamadas e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo de estacionamento de chamadas usando o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsCpsConfiguration** . Você não pode gerenciar as configurações do aplicativo de estacionamento de chamada usando o painel de controle do Lync Server.

**Reconfigurar as definições do serviço de estacionamento de chamadas**

1.  No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
    <div>
    

    > [!NOTE]  
    > Se as configurações do aplicativo de estacionamento de chamada do Lync Server 2013 forem idênticas às configurações herdadas do Lync Server 2010, você poderá ignorar a execução desta etapa. Se as configurações do aplicativo de estacionamento de chamada forem diferentes para os ambientes do Lync Server 2013 e do Lync Server 2010, use o cmdlet abaixo como um modelo para atualizar essas alterações.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> "```

Para reatribuir todos os intervalos de órbita de estacionamento de chamadas do pool do Lync Server 2010 ao pool do Lync Server 2013, você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

**Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o painel de controle do Lync Server**

1.  Abra o Painel de Controle do Lync Server.

2.  No painel esquerdo, selecione **recursos de voz**.

3.  Selecione a guia **estacionamento de chamada** .

4.  Para cada intervalo de órbita de estacionamento de chamada atribuído a um pool do Lync Server 2010, edite o **FQDN da configuração do servidor de destino** e selecione o pool do lync Server 2013 que processará as solicitações de estacionamento de chamadas.

5.  Selecione **confirmar** para salvar as alterações.

**Reatribuir todos os intervalos de órbita de estacionamento de chamadas usando o Shell de gerenciamento do Lync Server**

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    Este cmdlet lista todos os intervalos de órbita de estacionamento de chamada na implantação. Todas as órbitas de estacionamento de chamadas com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool do Lync Server 2010 devem ser reatribuídas.
    
    Para reatribuir os intervalos de órbita do estacionamento de chamadas do Lync Server 2010 ao pool do Lync Server 2013, na linha de comando, digite o seguinte:
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

Após reatribuir todos os intervalos de órbita de estacionamento de chamadas para o pool do Lync Server 2013, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o pool do Lync Server 2013 tratará de todas as solicitações de estacionamento de chamadas futuras.

</div>

<span> </span>

</div>

</div>

</div>

