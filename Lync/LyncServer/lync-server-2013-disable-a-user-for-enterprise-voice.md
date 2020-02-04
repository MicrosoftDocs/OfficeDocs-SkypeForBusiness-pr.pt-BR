---
title: 'Lync Server 2013: desabilitar um usuário para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Desabilitar um usuário para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para desabilitar uma conta de usuário para o Enterprise Voice

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6.  No menu **Editar**, clique em **Exibir detalhes**.

7.  Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.
    
    <div>
    

    > [!NOTE]  
    > Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em <STRONG>telefonia</STRONG>, clique em <STRONG>áudio/vídeo desabilitado</STRONG>.

    
    </div>

8.  Clique em **Confirmar**.

O usuário agora não pode usar o recurso Enterprise Voice.

</div>

<div>

## <a name="see-also"></a>Confira também


[Habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Gerenciando o Enterprise Voice para usuários no Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Shell de Gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

