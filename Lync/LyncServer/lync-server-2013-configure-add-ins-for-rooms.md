---
title: 'Lync Server 2013: Configurar suplementos para salas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurar suplementos para salas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

No painel de controle do Lync Server 2013, você pode usar a seção de **suplemento** da página de **chat persistente** para associar URLs a salas de chat persistentes. Essas URLs aparecem no cliente do Lync 2013 na sala de chat no painel de extensibilidade de conversa. Um administrador deve adicionar suplementos à lista de suplementos registrados e os gerentes/autores da sala de chat devem associar salas a um dos suplementos registrados antes que os usuários possam ver essa atualização em seu cliente Lync 2013.

Os suplementos são usados para estender a experiência na sala. Um suplemento típico pode incluir uma URL apontando para um aplicativo do Silverlight que intercepta quando um marcador de ação é publicado em uma sala de chat e mostra o histórico de ações no painel extensibilidade. Outros exemplos incluem a URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Para configurar Suplementos para as salas de chat

1.  A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar cmdlets do Windows PowerShell. Para obter detalhes, consulte Configurando o <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e depois em **Suplemento**.
    
    Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.

4.  Na página  **Suplementos**, clique em **Novo**.

5.  Em **selecionar um serviço**, selecione o serviço correspondente ao pool de servidores de chat persistente em que você precisa criar o suplemento. Suplementos não podem ser movidos de um pool a outro nem compartilhado entre pools diferentes.

6.  Em **Suplementos novos**, faça o seguinte:
    
      - Em **Nome**, especifique um nome para o novo suplemento.
    
      - Em **URL**, especifique a URL que deve ser associada ao suplemento. As URLs são limitadas aos protocolos http e https.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Abrir ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configurando Servidor de Chat Persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

