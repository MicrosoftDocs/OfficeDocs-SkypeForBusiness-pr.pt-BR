---
title: 'Lync Server 2013: Configurando a política de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6410e50a5e7d84de152b9a4e4bd1f962c5a3c9bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configurando a política de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

O Lync Server 2013 fornece políticas de mobilidade que determinam quem pode usar os recursos de mobilidade, ligar via trabalho, VoIP (voz sobre IP) ou vídeo e se o WiFi será necessário para VoIP ou vídeo. O recurso chamar via trabalho permite que um usuário móvel faça e receba chamadas em um telefone celular usando um número de telefone comercial em vez do número de telefone celular. Esse recurso impede que o participante chamado Veja o número de telefone celular do chamador e permite que o usuário Evite encargos de chamada de saída. A configuração de VoIP e vídeo possibilita que os usuários recebam e façam chamadas de VoIP e vídeo. Configurações para o uso de WiFi defina se o dispositivo de um usuário será solicitado a usar uma rede WiFi em uma rede de dados celular.

Por padrão, mobilidade, ligar via trabalho e VoIP e recursos de vídeo estão habilitados. As configurações para exigir WiFi para VoIp e vídeo estão desabilitadas. Os administradores podem determinar quem tem acesso a esses recursos executando um cmdlet. Você pode desabilitar as opções globalmente, por site ou por usuário.

Para poder usar os recursos de mobilidade e Telefonar via Trabalho, os usuários devem atender aos seguintes pré-requisitos:

  - Os usuários devem estar habilitados para o Lync Server 2013.

  - Os usuários devem ser habilitados para o Enterprise Voice.

  - Os usuários deve ser atribuídos a uma política de mobilidade que tem a opção **EnableMobility** definida como True.

Para que os usuários possam usar o Telefonar via Trabalho, eles devem atender aos dois seguintes pré-requisitos adicionais:

  - Os usuários deve ser atribuídos a uma política de voz tem a opção **Habilitar toques de telefones simultâneos** selecionada.

  - Os usuários deve ser atribuídos a uma política de mobilidade que tem a opção **EnableOutsideVoice** definida como True.

<div>


> [!NOTE]  
> Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas do Lync para o Lync Voice over IP (VoIP) ou podem participar de conferências usando o link Clique para ingressar em seus dispositivos móveis, se você atribuir a esses usuários as opções apropriadas para política de voz. Para obter detalhes, consulte <A href="lync-server-2013-defining-your-mobility-requirements.md">definindo seus requisitos de mobilidade para o Lync Server 2013</A>.



</div>

Para obter detalhes sobre como habilitar usuários para o Lync Server 2013, confira [desabilitar ou reabilitar a conta de usuário do Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Para obter detalhes sobre como habilitar usuários para o Enterprise Voice, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Para obter detalhes sobre como definir as opções de política de voz, consulte [Modify a Voice Policy and configure PSTN Usage Records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Para modificar a política global de mobilidade

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Desabilite o acesso à mobilidade e Telefonar via Trabalho globalmente. Na linha de comando, digite:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Você pode desabilitar o Telefonar via Trabalho sem desativar o acesso à mobilidade. No entanto, você não pode desabilitar a mobilidade sem também desabilitar o Telefonar via Trabalho.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Para modificar a política de mobilidade por site

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Crie uma política de nível de site e desative VoIP e vídeo e habilite exigir WiFi para áudio IP e vídeo IP por site. Na linha de comando, digite:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Para modificar a política de mobilidade por usuário

1.  Faça logon em qualquer computador em que o Shell de gerenciamento do Lync Server e o OCScore estão instalados como um membro da função CsAdministrator.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Crie políticas de nível de mobilidade do usuário e desabilite a mobilidade e o o Telefonar via Trabalho por usuário. Na linha de comando, digite:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Você pode desabilitar o Telefonar via Trabalho sem desativar o acesso à mobilidade. No entanto, você não pode desabilitar a mobilidade sem também desabilitar o Telefonar via Trabalho.
    
    Por exemplo:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Consulte também


[Desabilitar ou reabilitar a conta de usuário do Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Habilitar usuários para o Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definindo seus requisitos de mobilidade para o Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


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

