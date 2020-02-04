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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-08-07_

Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de Voz**, execute este procedimento para examinar, publicar ou cancelar as alterações pendentes.

<div>


> [!IMPORTANT]  
> Certifique-se de que somente um usuário por vez modifique as definições de configurações do Roteamento de voz.<BR>Todas as alterações pendentes devem ser publicadas ao mesmo tempo, executando o comando <STRONG>Confirmar todos</STRONG>. Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando <STRONG>Revisar alterações não confirmadas</STRONG> e cancele qualquer alteração de configuração que não deseja publicar.<BR>Se você navegar longe das páginas do grupo <STRONG>Roteamento de voz</STRONG> antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdida. No entanto, é possível exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, consulte <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exportar um arquivo de configuração de rota de voz no Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar as alterações de configuração do roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz**.

4.  Faça as alterações de configuração que deseja para as configurações em cada página do grupo **Roteamento de voz**.

5.  Para revisar as alterações pendentes sem publicá-las, selecione **Revisar alterações não confirmadas** no menu **Confirmar**.

6.  Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:
    
      - Selecione **Cancelar todas as alterações não confirmadas** no menu **Confirmar**.
    
      - Navegue até a guia da página **Roteamento de voz** que possui as alterações pendente que deseja cancelar, selecione o item com as alterações pendentes, clique em **Confirmar** e em **Cancelar alterações selecionadas**.

7.  Após revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em **Confirmar** e em **Confirmar todas**.

8.  Na caixa de diálogo **Definições da configuração de voz não confirmadas** que exibe uma lista de todas as alterações pendentes, clique em **OK**.
    
    Quando o painel de controle do Lync Server tiver confirmado as alterações, a mensagem de **configuração de roteamento de voz publicada com êxito** será exibida.

</div>

</div>

<span> </span>

</div>

</div>

</div>

