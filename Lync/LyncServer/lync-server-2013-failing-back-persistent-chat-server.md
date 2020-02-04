---
title: 'Lync Server 2013: Fallback do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca00a71c88b917b9e59f2e9039e7960b51f64157
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Fallback do Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

Este procedimento descreve as etapas necessárias para recuperar-se de uma falha persistente do servidor de chat e para restabelecer as operações do data center principal.

Durante uma falha persistente do servidor de chat, o data center principal sofre uma interrupção completa, e os bancos de dados principal e espelho ficam indisponíveis. O data center primário faz failover para o servidor de backup.

O procedimento a seguir restaura a operação normal após o backup do data center primário e a recompilação dos servidores. O procedimento pressupõe que o principal centro de dados foi recuperada da interrupção total, e que o banco de dados MGC e o banco de dados do mgccomp foram recriados e reinstalados usando o construtor de topologias.

O procedimento também pressupõe que nenhum novo espelho e servidores de backup foram implantados durante o período de failover e que o único servidor implantado é o servidor de backup e seu servidor de espelhamento, conforme definido em falha em um [servidor de chat persistente no Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>Para fazer failback do servidor de chat persistente

1.  Desmarque todos os servidores da lista de servidores de chat persistentes usando `Set-CsPersistentChatActiveServer` o cmdlet do Shell de gerenciamento do Lync Server. Isso interrompe a conexão de todos os servidores de chat persistentes ao banco de dados do MGC e do banco de dados do mgccomp durante o failback.
    
    <div>
    

    > [!IMPORTANT]  
    > O agente do SQL Server no servidor back-end persistente do servidor de chat secundário deve estar em execução em uma conta privilegiada. Em termos específicos, a conta deve incluir: 
    > <UL>
    > <LI>
    > <P>Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.</P>
    > <LI>
    > <P>Acesso para gravação ao diretório local específico em que os backups serão copiados.</P></LI></UL>

    
    </div>

2.  Desabilite o espelhamento no banco de dados mgc de backup:
    
    1.  Usando o SQL Server Management Studio, conecte-se à instância MGC de backup.
    
    2.  Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.
    
    3.  Clique em **Remover Espelhamento**.
    
    4.  Clique em **OK**.
    
    5.  Execute as mesmas etapas com o banco de dados mgccomp.

3.  Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:
    
    1.  Usando o SQL Server Management Studio, conecte-se à instância MGC de backup.
    
    2.  Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.
    
    3.  Em **Tipo de backup**, selecione **Completo**.
    
    4.  Para **Componente de backup**, clique em **Banco de dados**.
    
    5.  Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.
    
    6.  * \<Opcionais\> * Em **Descrição**, digite uma descrição do conjunto de backup.
    
    7.  Remova o local de backup padrão da lista de destino.
    
    8.  Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.
    
    9.  Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.

4.  Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.
    
    1.  Usando o SQL Server Management Studio, conecte-se à instância principal do MGC.
    
    2.  Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.
    
    3.  Selecione **Do dispositivo**.
    
    4.  Clique no botão Procurar, que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.
    
    5.  Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.
    
    6.  Clique em **Opções** no painel **Selecionar uma página**.
    
    7.  Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.
    
    8.  Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.
    
    9.  Clique em **OK** para iniciar o processo de restauração.

5.  Configurar o envio de log do SQL Server para o banco de dados principal. Siga os procedimentos em [Configurando o servidor de chat persistente para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para estabelecer o envio de log para o banco de dados principal do MGC.

6.  Defina os servidores ativos do servidor de chat persistente. No Shell de gerenciamento do Lync Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados.

    
    </div>

O estado restaurar o pool em seu estado normal execute o seguinte comando do Windows PowerShell:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Consulte o tópico da ajuda para o cmdlet [set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) para obter mais informações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

