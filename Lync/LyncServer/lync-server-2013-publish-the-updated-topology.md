---
title: 'Lync Server 2013: Postar a topologia atualizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Postar a topologia atualizada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Depois de atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o servidor de chat persistente. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.

<div>

## <a name="to-publish-an-updated-topology"></a>Para publicar uma topologia atualizada

Antes de publicar sua topologia, instale os bancos de dados do servidor de chat persistente. Use o construtor de topologias para instalar bancos de dados selecionando **ação** e **instalar banco de dados**.

1.  Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** , e que tem permissões de controle total (ou seja, ler, gravar e modificar) no repositório de arquivos a ser usado para o repositório de arquivos do servidor de chat persistente (para que o construtor de topologias possa configurar as listas de controle de acesso discricional (DACLs) necessárias ou uma conta com direitos de usuário equivalentes.

2.  Iniciar o construtor de topologias. Selecione **baixar a topologia de implantação existente**ou **abrir a topologia de um arquivo local** se você salvá-lo localmente.

3.  Na árvore de console, clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar topologia**.

4.  Na página **Publicar a topologia**, clique em **Avançar**.

5.  Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > Após publicar a topologia, você deve configurar o suporte para o servidor de chat persistente antes que qualquer conteúdo possa ser arquivado.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

