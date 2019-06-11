---
title: Configurando a qualidade do serviço em dispositivos Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configurando a qualidade do serviço em dispositivos Microsoft Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Embora a QoS (qualidade de serviço) não seja habilitada por padrão para dispositivos como iPhones, a QoS é habilitada por padrão para dispositivos que executam o Lync Phone Edition. (Esses dispositivos são comumente referidos como telefones de comunicação unificada ou UC.) Para verificar isso, execute o seguinte comando do Windows PowerShell no Shell de gerenciamento do Lync Server:

    Get-CsUCPhoneConfiguration

Se você não fez nenhuma alteração nas configurações de seu telefone UC, receberá as informações que se assemelharão a isto:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Para fins de qualidade de serviço, apenas uma dessas propriedades é de interesse: VoiceDiffServTag. O VoiceDiffServTag representa o valor de DSCP atribuído ao tráfego de voz que emana de um dispositivo Lync Phone Edition.

<div>


> [!NOTE]
> O parâmetro Voice8021p não é mais compatível com o Lync Server 2013. O parâmetro ainda é válido para fins de compatibilidade com versões anteriores do Microsoft Lync Server 2010; no entanto, ele não tem efeito em dispositivos usados com o Lync Server 2013.



</div>

Na maioria das redes, a marcação de pacotes do Lync Phone Edition com um VoiceDiffServTag de 40 não deve causar problemas. No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46. Para manter a consistência em toda a sua rede, talvez você queira alterar a propriedade VoiceDiffServTag de seus telefones UC para o 46.

Para fazer isso, você pode usar o Windows PowerShell ou o painel de controle do Lync Server. Para modificar o valor VoiceDiffServTag usando o Windows PowerShell, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

O comando anterior modifica o conjunto global de configurações de configuração de telefone de comunicação unificada. No entanto, observe que as configurações de telefone UC também podem ser atribuídas ao escopo do site. Para modificar as configurações de telefone UC no escopo do site, você deve especificar a identidade do site. Por exemplo:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Você também pode usar o comando a seguir para modificar simultaneamente todas as suas configurações de telefone UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Se você preferir fazer essa alteração usando o painel de controle do Lync Server, inicie o painel de controle e, em seguida, conclua o seguinte procedimento:

1.  Clique em **clientes** e em **configuração de dispositivo**.

2.  Na guia **configuração de dispositivo** , clique duas vezes na coleção de configurações que você deseja modificar (por exemplo, **global**).

3.  Na caixa de diálogo **Editar configuração de dispositivo** , defina o valor da **caixa QoS (qualidade de serviço) de voz** como **46** e clique em **confirmar**.

Se você tiver várias coleções, será necessário repetir esse processo para cada conjunto de configurações de telefone UC. O painel de controle do Lync Server não permitirá que você modifique simultaneamente várias coleções de configurações.

Se você tiver dispositivos que não são baseados no sistema operacional Windows (por exemplo, iPhones) em sua organização, esses dispositivos não serão afetados alterando a configuração VoiceDiffServTag. Se você quiser alterar os valores de DSCP nesses dispositivos, será necessário consultar o manual de administração para cada um dos seus tipos de dispositivo.

</div>

<span> </span>

</div>

</div>

</div>

