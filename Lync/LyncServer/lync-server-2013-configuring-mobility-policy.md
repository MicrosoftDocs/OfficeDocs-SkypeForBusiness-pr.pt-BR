---
title: 'Lync Server 2013: Configurando a política de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configurando a política de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

O Lync Server 2013 fornece políticas de mobilidade que determinam quem pode usar recursos de mobilidade, chamadas por meio de trabalho, voz sobre IP (VoIP) ou vídeo e se o WiFi será necessário para VoIP ou vídeo. A chamada via recurso de trabalho permite que um usuário móvel faça e receba chamadas em um celular usando um número de telefone comercial, em vez do número de telefone celular. Esse recurso impede que a parte chamada Veja o número de telefone celular do chamador e permite que um usuário Evite cobranças de chamadas de saída. A configuração de VoIP e vídeo possibilita que os usuários recebam e façam chamadas e vídeos de VoIP. Configurações para uso WiFi defina se o dispositivo de um usuário será necessário para usar uma rede WiFi em uma rede de dados da rede celular.

Por padrão, a mobilidade, a chamada por meio do trabalho e os recursos de vídeo e VoIP são habilitados. As configurações para exigir WiFi para VoIp e vídeo estão desativadas. Os administradores podem determinar quem tem acesso a esses recursos executando um cmdlet. Você pode desativar as opções de modo global, por site ou por usuário.

Para poder usar os recursos de mobilidade e ligar pelo trabalho, os usuários devem atender aos seguintes pré-requisitos:

  - Os usuários devem ser habilitados para o Lync Server 2013.

  - Os usuários devem ser habilitados para o Enterprise Voice.

  - Os usuários devem receber uma política de mobilidade com a opção **EnableMobility** definida como true.

Para que os usuários possam usar a chamada por meio do trabalho, eles devem atender aos dois pré-requisitos adicionais a seguir:

  - Os usuários devem receber uma política de voz com a opção **habilitar o toque simultâneo de telefones** selecionada.

  - Os usuários devem receber uma política de mobilidade com a opção **EnableOutsideVoice** definida como true.

<div>


> [!NOTE]  
> Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas do Lync para o protocolo de voz sobre IP (VoIP) ou podem participar de conferências usando o link clicar para ingressar em seus dispositivos móveis, se você atribuir a esses usuários as opções apropriadas para a política de voz. Para obter detalhes, consulte <A href="lync-server-2013-defining-your-mobility-requirements.md">definindo seus requisitos de mobilidade para o Lync Server 2013</A>.



</div>

Para obter detalhes sobre como habilitar usuários do Lync Server 2013, consulte [desabilitar ou habilitar novamente a conta de usuário para o Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Para obter detalhes sobre como habilitar usuários do Enterprise Voice, consulte [habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Para obter detalhes sobre a configuração de opções de política de voz, consulte [modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Para modificar a política de mobilidade global

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Desative o acesso à mobilidade e faça chamadas por meio do trabalho global. Na linha de comando, digite:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade. No entanto, você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Para modificar a política de mobilidade por site

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Crie uma política no nível do site e desative VoIP e vídeo, e habilite exigir WiFi para áudio IP e vídeo por IP por site. Na linha de comando, digite:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Para modificar a política de mobilidade por usuário

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore são instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Crie políticas de mobilidade em nível de usuário e desative a mobilidade e a chamada por meio do trabalho por usuário. Na linha de comando, digite:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade. No entanto, você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho.
    
    Por exemplo:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Confira também


[Desabilitar ou habilitar novamente a conta de usuário para o Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definindo seus requisitos de mobilidade para Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

