---
title: Expansor das Configurações Gerais do Servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'No Construtor de Topologias, é possível editar as propriedades de um Arquivamento em execução em um servidor individual clicando com o botão direito do mouse no Arquivamento em execução em um servidor individual na árvore de console e clicando em Ação na barra de ferramentas, ou clicando em uma tarefa no painel Ações e clicando emEditar Propriedades e alterando qualquer uma das seguintes opções:'
ms.openlocfilehash: 9f68ed29d1ff58e3c89c5b5e50e83e8a8730a338
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220766"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="e356a-103">Expansor das Configurações Gerais do Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="e356a-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="e356a-104">No Construtor de Topologias, é possível editar as propriedades de um Arquivamento em execução em um servidor individual clicando com o botão direito do mouse no Arquivamento em execução em um servidor individual na árvore de console e clicando em **Ação** na barra de ferramentas, ou clicando em uma tarefa no painel Ações e clicando em**Editar Propriedades** e alterando qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e356a-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="e356a-105">**FQDN**, para alterar o nome de domínio totalmente qualificado (FQDN) do servidor que você deseja implantar como um Arquivamento em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="e356a-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="e356a-p101">**Repositório SQL**, para alterar a instância do SQL Server a ser usada para o banco de dados de arquivamento do SQL Server. Se você alterar o banco de dados do SQL Server de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="e356a-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="e356a-p102">**Compartilhamento de arquivos**, para alterar a pasta a ser usada para o repositório de arquivamento. Se você alterar o compartilhamento de arquivos de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor. Além disso, é necessário mover os arquivos de conferência anteriores para a nova pasta de repositório de arquivos a fim de evitar perda de arquivos de conferência arquivados.</span><span class="sxs-lookup"><span data-stu-id="e356a-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e356a-111">Para alterar os pools associados ao Arquivamento em execução no servidor, selecione a opção **Editar Propriedades** para o nó do pool de Front-Ends individual ou para o nó do Aparelho de Filial Persistente atualmente associado ao Arquivamento em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="e356a-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e356a-p103">O nó de Arquivamento conterá um Arquivamento em execução no servidor se antes você já tiver adicionado um Arquivamento para execução no servidor à topologia no Construtor de Topologias. É possível editar as propriedades de qualquer servidor que estiver executando o Arquivamento na lista. No entanto, não será possível arquivar mensagens instantâneas ou de webconferência (mensagens) até você configurar o serviço no servidor que estiver executando o Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e356a-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

