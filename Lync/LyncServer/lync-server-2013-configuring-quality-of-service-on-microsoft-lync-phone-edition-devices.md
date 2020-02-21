---
title: Configurando a qualidade de serviço nos dispositivos do Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configurando a qualidade de serviço nos dispositivos do Microsoft Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Embora a QoS (qualidade de serviço) não seja habilitada por padrão para dispositivos como iPhones, a QoS é habilitada por padrão para dispositivos que executam o Lync Phone Edition. (Esses dispositivos são comumente chamados de telefones UC ou Unificação de comunicação). Para verificar isso, execute o seguinte comando do Windows PowerShell de dentro do Shell de gerenciamento do Lync Server:

    Get-CsUCPhoneConfiguration

Se você não fizer nenhuma alteração em suas configurações de telefone UC, então você receberá informações de volta como essas:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Para fins de Qualidade de Serviço, apenas uma dessas propriedades é de interesse: VoiceDiffServTag. O VoiceDiffServTag representa o valor de DSCP atribuído ao tráfego de voz que provém de um dispositivo do Lync Phone Edition.

<div>


> [!NOTE]
> O parâmetro Voice8021p não tem mais suporte no Lync Server 2013. O parâmetro ainda é válido para compatibilidade com versões anteriores com o Microsoft Lync Server 2010; no entanto, não tem efeito em dispositivos usados com o Lync Server 2013.



</div>

Na maioria das redes, a marcação de pacotes do Lync Phone Edition com um VoiceDiffServTag de 40 não deve causar problemas. No entanto, 40 não é o valor geralmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46. Para manter a consistência em toda a rede, você pode alterar a propriedade VoiceDiffServTag dos seus telefones UC para 46.

Para fazer isso, você pode usar o Windows PowerShell ou o painel de controle do Lync Server. Para modificar o valor VoiceDiffServTag usando o Windows PowerShell, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

O comando anterior redefine a coleção global das configurações do telefone UC. Observe, no entanto, que as configurações do telefone UC podem também ser atribuídas ao escopo do site. Para modificar as configurações do telefone UC no escopo do site, é necessário especificar a identidade do site. Por exemplo:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Você pode também usar o seguinte comando para modificar simultaneamente suas configurações de telefone UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Se você preferir fazer essa alteração usando o painel de controle do Lync Server, inicie o painel de controle e conclua o procedimento a seguir:

1.  Clique em **Clientes** e depois em **Configuração de Dispositivo**.

2.  Na guia **Configuração de Dispositivo**, clique duas vezes na coleção de configurações que deseja modificar (por exemplo, **Global**).

3.  Na caixa de diálogo **Editar Configuração de Dispositivo**, defina o valor da caixa **Qualidade de serviço (QoS) de voz** para **46** e depois clique em **Confirmar**.

Se você tiver várias coleções, será necessário repetir esse processo para cada coleção de configurações de telefone UC. O painel de controle do Lync Server não permitirá que você modifique várias coleções de configurações simultaneamente.

Se você tiver dispositivos que não são baseados no sistema operacional Windows (como iPhones), esses dispositivos em sua organização não serão afetados pela mudança da configuração do VoiceDiffServTag. Se desejar alterar os valores DSCP nesses dispositivos, será necessário consultar o manual de administração para cada um de seus tipos de dispositivos.

</div>

<span> </span>

</div>

</div>

</div>

