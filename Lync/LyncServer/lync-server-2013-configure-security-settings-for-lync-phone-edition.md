---
title: 'Lync Server 2013: definir configurações de segurança para o Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Ajude a melhorar a segurança dos dispositivos que executam o Lync Phone Edition por meio da configuração de segurança SIP e das configurações de bloqueio de telefone.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Para definir as configurações de segurança do Lync Phone Edition

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e em **configuração de dispositivo**.

4.  Na página **configuração de dispositivo** , na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de segurança.

5.  Em **Editar configuração de dispositivo**, na **segurança SIP**, especifique o nível de segurança SIP. O nível padrão é **alto**, o que recomendamos usar.

6.  Em **Editar configuração de dispositivo**, em **bloqueio de telefone**, marque ou desmarque a caixa de seleção **impor bloqueio de dispositivo** (marcada por padrão) e especifique o comprimento mínimo do PIN (6 caracteres por padrão) e período de tempo limite (10 minutos por padrão). Recomendamos usar esses padrões ou aumentar o comprimento do PIN e/ou reduzir o período de tempo limite.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes, consulte <A href="lync-server-2013-enforce-phone-locking.md">reforçar o bloqueio de telefone no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Definir configurações de segurança para os telefones do Lync Phone Edition usando cmdlets do Windows PowerShell

As configurações de segurança podem ser gerenciadas usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-modify-the-sip-security-mode"></a>Para modificar o modo de segurança SIP

  - Esse comando define o SIPSecurityMode para o conjunto global de configurações de telefone UC para médio. A segurança SIP também pode ser definida como baixa ou alta (o valor padrão).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Para modificar o comprimento mínimo do PIN

  - Neste exemplo, todas as configurações de telefone UC são modificadas para exigir um comprimento mínimo de PIN de 7 dígitos.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando a autenticação do Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

