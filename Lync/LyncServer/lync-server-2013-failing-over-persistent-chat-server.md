---
title: 'Lync Server 2013: failover do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Failover do servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

O failover do servidor de chat persistente foi projetado para ser principalmente um processo manual.

O procedimento de failover é baseado na pressuposição de que o data center secundário está funcionando, mas os serviços do servidor de chat persistente onde o banco de dados de chat persistente principal está localizado não estão totalmente disponíveis, incluindo o seguinte:

  - Banco de dados primário do servidor de chat persistente e banco de dados de espelho do servidor de chat persistente estão inoperante.

  - O servidor front-end do Lync Server está inoperante.

O procedimento é baseado em duas etapas básicas:

  - Recupere o banco de dados de chat persistente principal (MGC).

  - Estabelecer o espelhamento para o novo banco de dados primário.

O banco de dados de conformidade de chat persistente (mgccomp) não tem failover. O conteúdo deste banco de dados é temporário e é excluído como os processos do adaptador de conformidade dos dados. É sua responsabilidade, como administrador de chat persistente, gerenciar corretamente a saída do adaptador para evitar a perda de dados.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Para fazer failover do servidor de chat persistente

1.  Remova o envio de logs do banco de dados de envio de log de backup do servidor de chat persistente.
    
    1.  Usando o SQL Server Management Studio, conecte-se à instância de banco de dados onde o banco de dados de backup do servidor de chat persistente MGC está localizado.
    
    2.  Abra uma janela de consulta para o banco de dados principal.
    
    3.  Use o seguinte comando para derrubar o envio de log:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.

3.  Aplique qualquer backup do log de transação não aplicado na sequência para o banco de dados secundário. Para obter detalhes, consulte "como aplicar um backup de log de transação (Transact-SQL)" http://go.microsoft.com/fwlink/p/?linkid=247428em.

4.  Coloque o banco de dados de gerenciamento de backup online. Usando a janela de consulta que abra na etapa 1b, faça o seguinte:
    
    1.  Finalize todas as conexões com o banco de dados de gerenciamento, se houver:
        
        1.  **exec SP\_who2** para identificar as conexões com o banco de dados MGC.
        
        2.  **Kill \<spid\> ** para encerrar essas conexões.
    
    2.  Coloque o banco de dados online:
        
        1.  **restaure o banco de dados MGC com a recuperação**.

5.  No Shell de gerenciamento do Lync Server, use o comando **set-CsPersistentChatState-Identity "Service: ATL-cs-001.litwareinc.com" – poolstate FailedOver** para failover para o banco de dados de backup do MGC. Certifique-se de substituir o nome de domínio totalmente qualificado do seu pool de chat persistente para o atl-cs-001.litwareinc.com.
    
    O banco de dados de backup de gerenciamento agora serve como o banco de dados primário.

6.  No Shell de gerenciamento do Lync Server, use o cmdlet **install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que funcionará agora como o banco de dados primário. Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho. Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração. Para obter detalhes, consulte a seção "usando os cmdlets do Shell de gerenciamento do Lync Server" em [implantando o espelhamento SQL para alta disponibilidade do servidor back-end no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Defina os servidores ativos do servidor de chat persistente. No Shell de comando do Lync Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os servidores ativos devem estar localizados dentro do mesmo centro de dados que o novo banco de dados primário ou em um centro de dados que possui uma conexão de baixa latência/alta largura de banda para o banco de dados.

    
    </div>
    
    Neste ponto, o failover do banco de dados primário do servidor de chat persistente para o banco de dados de backup do servidor de chat persistente é concluído com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

