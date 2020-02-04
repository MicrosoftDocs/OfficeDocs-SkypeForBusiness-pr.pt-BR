---
title: 'Lync Server 2013: Failover do Servidor de Chat Persistente'
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
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Failover do Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

O failover do servidor de chat persistente foi projetado para ser principalmente um processo manual.

O procedimento de failover baseia-se na pressuposição de que o centro de dados secundário está em funcionamento, mas os serviços persistentes do servidor de chat em que o banco de dados de chat persistente primário está localizado não estão disponíveis, incluindo o seguinte:

  - Banco de dados persistente do servidor de chat e banco de dados persistente do servidor de chat persistente estão inativos.

  - O servidor front-end do Lync Server está inoperante.

O procedimento é baseado em duas etapas básicas:

  - Recuperar o banco de dados de chat persistente primário (MGC).

  - Estabelecer o espelhamento para o novo banco de dados primário.

O banco de dados de conformidade de chat persistente (mgccomp) não apresentou failover. O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados. É sua responsabilidade, como administrador de chat persistente, gerenciar corretamente a saída do adaptador para evitar perda de dados.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Para fazer failover do servidor de chat persistente

1.  Remova o envio de log do banco de dados de envio de log de backup persistente do servidor de chat.
    
    1.  Usando o SQL Server Management Studio, conecte-se à instância do banco de dados em que o banco de dados de backup do servidor de chat persistente MGC está localizado.
    
    2.  Abra uma janela Consulta para o banco de dados mestre.
    
    3.  Use o seguinte comando para remover o envio de logs:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.

3.  Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário. Para obter detalhes, consulte "como aplicar um backup de log de transação (Transact-SQL)" http://go.microsoft.com/fwlink/p/?linkid=247428em.

4.  Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:
    
    1.  Encerre todas as conexões com o banco de dados mgc, se houver:
        
        1.  **exec SP\_who2** para identificar as conexões com o banco de dados MGC.
        
        2.  **eliminar \<spid\> ** para encerrar essas conexões.
    
    2.  Coloque o banco de dados online:
        
        1.  **Restaurar Banco de Dados mgc com recuperação**.

5.  No Shell de gerenciamento do Lync Server, use o comando **set-CsPersistentChatState-Identity "Service: ATL-cs-001.litwareinc.com" – poolstate FailedOver** para fazer failover para o banco de dados de backup do MGC. Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.
    
    O banco de dados de backup mgc agora serve como o banco de dados primário.

6.  No Shell de gerenciamento do Lync Server, use o cmdlet **install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora funciona como o banco de dados principal. Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho. Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração. Para obter detalhes, consulte a seção "usando cmdlets do Shell de gerenciamento do Lync Server" em [implantando o espelhamento do SQL para servidor back-end alta disponibilidade no Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Defina os servidores ativos do servidor de chat persistente. No Shell de comando do Lync Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.

    
    </div>
    
    Nesse ponto, o failover do banco de dados primário do servidor de chat persistente para o banco de dados de backup do servidor de chat persistente é concluído com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

