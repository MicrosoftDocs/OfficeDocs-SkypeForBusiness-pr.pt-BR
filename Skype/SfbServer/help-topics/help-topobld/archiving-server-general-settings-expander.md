---
title: Expansor das Configurações Gerais do Servidor de Arquivamento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'No construtor de topologias, você pode editar as propriedades de um servidor individual que esteja executando o arquivamento clicando com o botão direito do mouse no servidor que executa o arquivamento na árvore de console e clicando em ação na barra de ferramentas ou clicando em uma tarefa no painel Ações e, em seguida, clicando em Editar propriedades e alterando qualquer uma das seguintes opções:'
ms.openlocfilehash: d160b9e7294719ff2251e95e5cc2ab72dd3a6ffd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216892"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="61082-103">Expansor das Configurações Gerais do Servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="61082-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="61082-104">No construtor de topologias, você pode editar as propriedades de um servidor individual que esteja executando o arquivamento clicando com o botão direito do mouse no servidor que executa o arquivamento na árvore de console e clicando em **ação** na barra de ferramentas ou clicando em uma tarefa no painel Ações e, em seguida, clicando em **Editar propriedades** e alterando qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="61082-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="61082-105">**FQDN**, para alterar o nome de domínio totalmente qualificado (FQDN) do servidor que você deseja implantar como um Arquivamento em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="61082-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="61082-p101">**Repositório SQL**, para alterar a instância do SQL Server a ser usada para o banco de dados de arquivamento do SQL Server. Se você alterar o banco de dados do SQL Server de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="61082-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="61082-p102">**Compartilhamento de arquivo**, para alterar a pasta a ser usada para o repositório de arquivamento. Se você alterar o compartilhamento de arquivos de um Arquivamento em execução no servidor, será necessário reiniciar o Arquivamento em execução no servidor para garantir que a alteração entre em vigor. Além disso, é necessário mover os arquivos de conferência anteriores para a nova pasta de repositório de arquivos a fim de evitar perda de arquivos de conferência arquivados.</span><span class="sxs-lookup"><span data-stu-id="61082-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="61082-111">Para alterar os pools associados ao Arquivamento em execução no servidor, selecione a opção **Editar Propriedades** para o nó do pool Front End individual ou o nó Aparelho de Filial Persistente atualmente associado ao Arquivamento em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="61082-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61082-112">O nó Arquivamento conterá um Arquivamento em execução no servidor se você tiver adicionado anteriormente um Arquivamento em execução no servidor à topologia no Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="61082-112">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder.</span></span> <span data-ttu-id="61082-113">É possível editar as propriedades de qualquer Arquivamento em execução no servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="61082-113">You can edit properties for any server running Archiving in the list.</span></span> <span data-ttu-id="61082-114">No entanto, mensagens instantâneas ou webconferência (mensagens) não podem ser arquivadas até que você também configure o serviço para o arquivamento em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="61082-114">However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

