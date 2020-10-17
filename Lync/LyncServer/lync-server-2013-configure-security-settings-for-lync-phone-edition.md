---
title: 'Lync Server 2013: configurar definições de segurança para o Lync Phone Edition'
description: 'Lync Server 2013: configurar definições de segurança para o Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564347"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Ajuda a melhorar a segurança de dispositivos que executam o Lync Phone Edition através da configuração de segurança SIP e das configurações de bloqueio de telefone.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Para definir as configurações de segurança para o Lync Phone Edition

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e em **Configuração dos dispositivo**.

4.  Na página **Configuração de Dispositivo**, na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de segurança.

5.  Em **Editar Configuração dos Dispositivos**, em **Segurança SIP**, especifique o nível de segurança SIP. O nível padrão é **Alto** (recomendado).

6.  Em **Editar Configuração dos Dispositivos**, em **Bloqueio de Telefone**, selecione ou desmarque a caixa de seleção **Impor bloqueio de dispositivo** (selecionada por padrão) e especifique o tamanho mínimo do PIN (seis caracteres por padrão) e o período de tempo limite (10 minutos por padrão). Recomendamos usar esses padrões ou aumentar o tamanho do PIN e/ou reduzir o período de tempo limite.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes, consulte <A href="lync-server-2013-enforce-phone-locking.md">impor bloqueio de telefone no Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Configurando definições de segurança para o Lync Phone Edition phones usando cmdlets do Windows PowerShell

As configurações de segurança podem ser gerenciadas usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-modify-the-sip-security-mode"></a>Para modificar o modo de segurança SIP

  - Este comando define SIPSecurityMode para o conjunto global de configurações de telefone UC como Médio. A segurança SIP também pode ser definida como Baixo ou Alto (valor padrão).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Para modificar o tamanho mínimo do PIN

  - Neste exemplo, todas as configurações do telefone UC são modificadas para exigir um PIN com tamanho mínimo de sete dígitos.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando a autenticação do Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

