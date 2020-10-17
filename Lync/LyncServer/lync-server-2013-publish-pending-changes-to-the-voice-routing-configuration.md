---
title: 'Lync Server 2013: publicar alterações pendentes na configuração de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3202bb936f7165047b968b979b49b036be574140
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512378"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-07_

Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de voz** , execute este procedimento para revisar, publicar ou cancelar as alterações pendentes.

<div>


> [!IMPORTANT]  
> Certifique-se de que somente um usuário por vez modifique as definições de configuração de roteamento de voz.<BR>Todas as alterações pendentes devem ser publicadas ao mesmo tempo executando o comando <STRONG>confirmar tudo</STRONG> . Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando <STRONG>revisar alterações não confirmadas</STRONG> e cancele as alterações de configuração que você não deseja publicar.<BR>Se você sair das páginas no grupo de <STRONG>Roteamento de voz</STRONG> antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdidas. No entanto, você pode exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, consulte <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exportar um arquivo de configuração de rota de voz no Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar alterações de configuração de roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz**.

4.  Faça as alterações de configuração que você deseja para as configurações em cada página do grupo de **Roteamento de voz** .

5.  Para revisar as alterações pendentes sem publicá-las, selecione **revisar alterações não confirmadas** no menu **confirmar** .

6.  Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:
    
      - Selecione **cancelar todas as alterações não confirmadas** no menu **confirmar** .
    
      - Navegue até a guia da página de **Roteamento de voz** que tem as alterações pendentes que você deseja cancelar, selecione o item com as alterações pendentes, clique em **confirmar**e em **cancelar alterações selecionadas**.

7.  Após revisar todas as alterações pendentes e cancelar as que você não deseja publicar, clique em **confirmar**e em **confirmar tudo**.

8.  Na caixa de diálogo **definições de configuração de voz não confirmadas** , que exibe uma lista de todas as alterações pendentes, clique em **OK**.
    
    Quando o painel de controle do Lync Server tiver confirmado as alterações, a mensagem de **configuração de roteamento de voz publicada com êxito** aparece.

</div>

</div>

<span> </span>

</div>

</div>

</div>

