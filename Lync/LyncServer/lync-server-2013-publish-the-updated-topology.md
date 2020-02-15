---
title: 'Lync Server 2013: publicar a topologia atualizada'
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
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Publicar a topologia atualizada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Depois de atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o servidor de chat persistente. Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.

<div>

## <a name="to-publish-an-updated-topology"></a>Para publicar uma topologia atualizada

Antes de publicar sua topologia, instale os bancos de dados do servidor de chat persistente. Use o construtor de topologias para instalar os bancos de dados selecionando **ação** e **instalar banco de dados**.

1.  Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo **Administradores de domínio** e do grupo **RTCUniversalServerAdmins** e que tem permissões de controle total (ou seja, leitura, gravação e modificação) no repositório de arquivos a ser usado para o repositório de arquivos do servidor de chat persistente (de modo que o construtor de topologia possa configurar as listas de controle de acesso discricional) ou uma conta com direitos de usuário equivalentes.

2.  Inicie o Construtor de topologia. Selecione **Baixar Topologia da implantação existente** ou **Abrir Topologia de um arquivo local** se tiver salvado localmente.

3.  Na árvore do console, clique com o botão direito do mouse em **Lync Server 2013**e clique em **publicar topologia**.

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

