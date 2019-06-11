---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>Migrar configurações do aplicativo do Estacionamento de Chamada

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

A migração do aplicativo de estacionamento de chamada do Lync Server 2010 para o Lync Server 2013 inclui a configuração do pool do Lync Server 2013 com qualquer música personalizada em arquivos de retenção que foram carregados no Lync Server 2010, a restauração das configurações de nível de serviço e o redirecionamento todas as órbitas de estacionamento de chamadas para o pool do Lync Server 2013. Se os arquivos de música em espera personalizados tiverem sido configurados no pool do Lync Server 2010, esses arquivos precisarão ser copiados para o novo pool do Lync Server 2013. Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera personalizados do Lync Server 2010 para outro destino para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para o parque da chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool do Lync Server 2010 para um repositório de arquivos do Lync Server 2013, use o comando **xcopy** com os seguintes parâmetros:

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Lync Server 2013, as configurações do aplicativo de estacionamento de chamada do pool do Lync Server 2013 devem ser configuradas, e as faixas órbitas do estacionamento de chamada associadas ao pool do Lync Server 2010 devem ser reatribuídas a o pool do Lync Server 2013.

As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de separação, habilitando ou desabilitando música em espera, o número máximo de tentativas de chamadas e a solicitação de tempo limite. Você deve gerenciar as configurações do aplicativo parque de chamadas usando o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsCpsConfiguration** . Não é possível gerenciar as configurações do aplicativo parque de chamadas usando o painel de controle do Lync Server.

**Reconfigurar as configurações de serviço do estacionamento de chamada**

1.  No servidor de front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
    <div>
    

    > [!NOTE]  
    > Se as configurações do aplicativo do Lync Server 2013 Call Park forem idênticas às configurações herdadas do Lync Server 2010, você poderá ignorar a execução desta etapa. Se as configurações do aplicativo de estacionamento de chamada forem diferentes para os ambientes Lync Server 2013 e Lync Server 2010, use o cmdlet abaixo como um modelo para atualizar essas alterações.

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

Para reatribuir todos os intervalos órbitas do parque de chamadas do pool do Lync Server 2010 ao pool do Lync Server 2013, você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

**Reatribuir todas as faixas órbitas do estacionamento de chamada usando o painel de controle do Lync Server**

1.  Abra o Painel de Controle do Lync Server.

2.  No painel esquerdo, selecione **recursos de voz**.

3.  Selecione a guia **estacionamento de chamadas** .

4.  Para cada intervalo de linha de plano de chamada atribuída a um pool do Lync Server 2010, edite a configuração **FQDN do servidor de destino** e selecione o pool do lync Server 2013 que processará as solicitações do parque de chamadas.

5.  Selecione **confirmar** para salvar as alterações.

**Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o Shell de gerenciamento do Lync Server**

1.  Abra o Shell de Gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsCallParkOrbit
    
    Esse cmdlet lista todos os intervalos de o parque de chamadas órbitas na implantação. Todas as órbitas do estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidas como o pool do Lync Server 2010 devem ser reatribuídas.
    
    Para reatribuir os intervalos de o parque de chamadas do Lync Server 2010 ao Lync Server 2013, na linha de comando, digite o seguinte:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

Depois de reatribuir todos os intervalos de chamadas de estacionamento de chamada para o pool do Lync Server 2013, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o pool do Lync Server 2013 atenderá a todas as solicitações de suporte ao parque do futuro.

</div>

<span> </span>

</div>

</div>

</div>

