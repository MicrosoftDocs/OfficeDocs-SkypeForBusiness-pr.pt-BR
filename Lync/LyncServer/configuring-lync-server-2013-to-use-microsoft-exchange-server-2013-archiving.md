---
title: Configurando o Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f557c95b9bf706b3a38b51bdbea4fea156b314
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503158"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="53d2f-102">Configurando o Microsoft Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="53d2f-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d2f-103">_**Última modificação do tópico:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="53d2f-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="53d2f-104">O Microsoft Lync Server 2013 oferece aos administradores a opção de ter as transcrições de mensagens instantâneas e webconferência arquivadas na caixa de correio do Microsoft Exchange Server 2013 de um usuário, em vez de em um banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="53d2f-105">Se você habilitar esta opção, as transcrições são gravadas na pasta Lixeira da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="53d2f-106">A pasta Lixeira é uma pasta oculta encontrada na pasta Itens Recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="53d2f-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="53d2f-107">Embora essa pasta não fique visível para os usuários finais, a pasta é indexada pelo mecanismo de pesquisa do Exchange e pode ser descoberta usando a pesquisa de caixa de correio do Exchange e/ou o Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53d2f-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="53d2f-108">Como as informações são armazenadas na mesma pasta usada pelo recurso de bloqueio do Exchange In-Place (responsável pelo arquivamento de email e outras comunicações do Exchange), os administradores podem usar uma única ferramenta para pesquisar todas as comunicações eletrônicas arquivadas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="53d2f-109">Para desabilitar completamente o arquivamento da conversa do Lync, você também deve desabilitar o histórico de conversas do Lync.</span><span class="sxs-lookup"><span data-stu-id="53d2f-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="53d2f-110">Para obter mais informações, consulte os seguintes tópicos: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and external Communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="53d2f-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="53d2f-111">Para arquivar transcrições no Exchange 2013, você deve começar Configurando a autenticação de servidor para servidor entre os dois servidores.</span><span class="sxs-lookup"><span data-stu-id="53d2f-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="53d2f-112">Depois que a autenticação de servidor para servidor estiver em vigor, você poderá realizar as seguintes tarefas no Microsoft Lync Server 2013 (Observe que, dependendo da configuração e da configuração, talvez não seja necessário concluir todas as tarefas):</span><span class="sxs-lookup"><span data-stu-id="53d2f-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="53d2f-113">Habilite o arquivamento do Exchange modificando suas definições de configuração de arquivamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="53d2f-114">Esta etapa é obrigatória para todas as implantações.</span><span class="sxs-lookup"><span data-stu-id="53d2f-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="53d2f-115">Habilitar o arquivamento para comunicações internas e/ou externas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="53d2f-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="53d2f-116">Esta etapa é obrigatória para todas as implantações.</span><span class="sxs-lookup"><span data-stu-id="53d2f-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="53d2f-117">Configurar a propriedade ExchangeArchivingPolicy para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="53d2f-118">Esta etapa só é necessária no Lync Server e o Exchange estão localizados em florestas diferentes.</span><span class="sxs-lookup"><span data-stu-id="53d2f-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="53d2f-119">Etapa 1: habilitar o arquivamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="53d2f-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="53d2f-120">O arquivamento no Lync Server é gerenciado principalmente usando as definições de configuração de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="53d2f-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="53d2f-121">Ao instalar o Lync Server 2013, você recebe automaticamente uma única coleção global dessas configurações.</span><span class="sxs-lookup"><span data-stu-id="53d2f-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="53d2f-122">(Os administradores podem, opcionalmente, criar novas coleções de configurações de arquivamento no escopo do site.) Por padrão, o arquivamento não está habilitado nas configurações globais, nem o arquivamento do Exchange está habilitado nessas configurações.</span><span class="sxs-lookup"><span data-stu-id="53d2f-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="53d2f-123">Para usar os administradores de arquivamento do Exchange deve configurar as propriedades EnableArchiving e EnableExchangeArchiving nessas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="53d2f-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="53d2f-124">A propriedade EnableArchiving pode ser definida para um dos seguintes três valores:</span><span class="sxs-lookup"><span data-stu-id="53d2f-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="53d2f-125">**Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-125">**None**.</span></span> <span data-ttu-id="53d2f-126">o Arquivamento é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="53d2f-126">Archiving is disabled.</span></span> <span data-ttu-id="53d2f-127">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="53d2f-127">This is the default value.</span></span> <span data-ttu-id="53d2f-128">Se EnableArchiving estiver definido como nenhum, nada será arquivado no seu banco de dados de arquivamento do Lync Server ou no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="53d2f-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="53d2f-129">**Inonly**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-129">**ImOnly**.</span></span> <span data-ttu-id="53d2f-130">Apenas transcrições de mensagem instantânea são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="53d2f-131">Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="53d2f-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="53d2f-132">Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="53d2f-133">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-133">**ImAndWebConf**.</span></span> <span data-ttu-id="53d2f-134">As transcrições de mensagem instantânea e de conferência da Web são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="53d2f-135">Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="53d2f-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="53d2f-136">Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="53d2f-137">A propriedade EnableExchangeArchiving é um valor booliano: defina EnableExchangeArchiving como true ($True) para habilitar o arquivamento do Exchange ou definir EnableExchangeArchiving como false ($False) para desabilitar o arquivamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="53d2f-138">Por exemplo, este comando habilita o arquivamento de transcrições de mensagens instantâneas e também habilita o arquivamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="53d2f-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="53d2f-139">Para desabilitar o arquivamento do Exchange, use um comando semelhante ao seguinte, que permite o arquivamento de mensagens instantâneas, mas desabilita o arquivamento para o Exchange (em outras palavras, as transcrições serão arquivadas no Lync Server):</span><span class="sxs-lookup"><span data-stu-id="53d2f-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="53d2f-140">Se a propriedade EnableArchiving estiver definida como nenhum, o Lync Server não arquivará as transcrições de mensagens instantâneas e Webconferência.</span><span class="sxs-lookup"><span data-stu-id="53d2f-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="53d2f-141">Neste caso, o servidor simplesmente ignora o valor configurado para EnableExchangeArchiving.</span><span class="sxs-lookup"><span data-stu-id="53d2f-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="53d2f-142">O arquivamento do Exchange também pode ser habilitado (ou desabilitado) usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="53d2f-143">Para fazer isso, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="53d2f-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="53d2f-144">No Painel de Controle, clique em **Monitoramento e Arquivamento** e clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="53d2f-145">Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).</span><span class="sxs-lookup"><span data-stu-id="53d2f-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="53d2f-146">No painel **Editar configuração de arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagem instantânea) ou **Arquivar sessões de IM e conferência da Web** (para arquivar sessões de mensagem instantânea e conferência da Web).</span><span class="sxs-lookup"><span data-stu-id="53d2f-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="53d2f-147">Após escolher os itens a serem arquivados, marque a caixa de seleção integração com o **Exchange Server** para habilitar o arquivamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="53d2f-148">Para desabilitar o arquivamento do Exchange, desmarque essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="53d2f-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53d2f-149">A caixa de seleção <STRONG>Integração do Exchange Server</STRONG> não estará disponível se a <STRONG>Configuração de arquivamento</STRONG> está definido para <STRONG>Desabilitar arquivamento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="53d2f-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="53d2f-150">Você deve habilitar o arquivamento primeiro e, em seguida, habilitar o arquivamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="53d2f-151">Se o Lync Server 2013 e o Exchange 2013 estiverem localizados na mesma floresta, o arquivamento para usuários individuais (ou pelo menos para usuários que tenham contas de email no Exchange 2013) será gerenciado usando as políticas de retenção do Exchange In-Place.</span><span class="sxs-lookup"><span data-stu-id="53d2f-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="53d2f-152">Se você tiver usuários hospedados em uma versão anterior do Exchange, o arquivamento desses usuários será gerenciado usando as políticas de arquivamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="53d2f-153">Observe que apenas usuários com contas no Exchange 2013 podem ter suas transcrições do Lync arquivadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="53d2f-154">Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, o arquivamento de usuários individuais será gerenciado pela configuração da propriedade ExchangeArchivingPolicy para cada conta de usuário individual.</span><span class="sxs-lookup"><span data-stu-id="53d2f-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="53d2f-155">Consulte a Etapa 3 para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="53d2f-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="53d2f-156">Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas</span><span class="sxs-lookup"><span data-stu-id="53d2f-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="53d2f-157">Depois de habilitar o arquivamento (e o arquivamento do Exchange), você deve modificar as políticas de arquivamento apropriadas para garantir que as sessões de usuário sejam realmente arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="53d2f-158">Observe que simplesmente habilitar o arquivamento (etapa 1) não faz com que o Lync Server comece a arquivar transcrições de mensagens instantâneas e webconferências.</span><span class="sxs-lookup"><span data-stu-id="53d2f-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="53d2f-159">Ao invés disso, você deve usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo.</span><span class="sxs-lookup"><span data-stu-id="53d2f-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="53d2f-160">Ao instalar o Lync Server 2013, você também instala uma política de arquivamento única e global que contém duas propriedades:</span><span class="sxs-lookup"><span data-stu-id="53d2f-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="53d2f-p119">**ArchiveInternal**. Quando definido para True ($True) indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="53d2f-p120">**ArchiveExternal**. Quando definido para True ($True) indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="53d2f-165">Por padrão, ambos os valores de propriedade são definidos para False, significando que as sessões de comunicação interna e externa não são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="53d2f-166">Para modificar a política global, você pode usar o Shell de gerenciamento do Lync Server e o cmdlet Set-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="53d2f-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="53d2f-167">Este comando habilita o arquivamento de sessões de comunicação interna e externa:</span><span class="sxs-lookup"><span data-stu-id="53d2f-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="53d2f-p122">Em alternativa, é possível usar New-CsArchivingPolicy para criar uma nova política no escopo local ou no escopo por usuário. Por exemplo, este comando cria uma nova política de arquivamento por usuário chamada RedmondArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="53d2f-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="53d2f-p123">Se você criar uma política por usuário, precisará atribuir esta política para os usuários adequados. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="53d2f-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="53d2f-172">As políticas de arquivamento também podem ser gerenciadas usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="53d2f-173">Dentro do Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="53d2f-174">Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar política de arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas** conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="53d2f-175">Para criar uma nova política de arquivamento, clique em **novo** e selecione política de **site** ou **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="53d2f-176">Se você criar uma nova política de usuário, deve acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir estes usuários com a nova política.</span><span class="sxs-lookup"><span data-stu-id="53d2f-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="53d2f-177">Etapa 3: Configurar a propriedade ExchangeArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="53d2f-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="53d2f-178">Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, não é suficiente simplesmente habilitar o arquivamento do Exchange nas definições de configuração de arquivamento; Isso não resultará em mensagens instantâneas e transcrições de webconferências sendo arquivadas no Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="53d2f-179">Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada uma das contas de usuário relevantes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="53d2f-180">Esta propriedade pode ser definida para uma dos quatro valores possíveis:</span><span class="sxs-lookup"><span data-stu-id="53d2f-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="53d2f-181">Não inicializado.</span><span class="sxs-lookup"><span data-stu-id="53d2f-181">Uninitialized.</span></span> <span data-ttu-id="53d2f-182">Indica que o arquivamento será baseado nas configurações de retenção de In-Place configuradas para a caixa de correio do Exchange do usuário; se In-Place bloqueio não tiver sido habilitado na caixa de correio do usuário, o usuário terá suas transcrições de mensagens e webconferência arquivadas no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="53d2f-183">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="53d2f-184">Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Lync Server, e não no Exchange.</span><span class="sxs-lookup"><span data-stu-id="53d2f-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="53d2f-185">**Noarquivamento**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-185">**NoArchiving**.</span></span> <span data-ttu-id="53d2f-186">Indica que as transcrições de mensagem instantânea e conferência da Web do usuário não devem ser arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53d2f-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="53d2f-187">Observe que essa configuração substitui as políticas de arquivamento do Lync Server atribuídas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="53d2f-188">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="53d2f-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="53d2f-189">Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Exchange independentemente das configurações de retenção de In-Place que tiverem (ou não) atribuídas à caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="53d2f-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="53d2f-190">Por exemplo, para configurar uma conta de usuário para que as transcrições de mensagens instantâneas e webconferências sejam sempre arquivadas no Exchange, você pode usar um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="53d2f-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="53d2f-191">Se você deseja definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool do Registrador específico), é possível usar um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="53d2f-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="53d2f-192">Observe que você deve usar o Shell de gerenciamento do Lync Server (e o Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="53d2f-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="53d2f-193">Essa propriedade não é exposta a administradores no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53d2f-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="53d2f-194">Se você deseja ver uma lista de todos os usuários atribuídos com uma política de arquivamento específica, é possível usar um comando semelhante ao seguinte, que retorna o nome de exibição do Active Directory de todos os usuários com a propriedade ExchangeArchivingPolicy definida para Não inicializado:</span><span class="sxs-lookup"><span data-stu-id="53d2f-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="53d2f-195">Da mesma forma, este comando retorna o nome de exibição dos usuários que não tem a propriedade ExchangeArchivingPolicy definida para UseLyncArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="53d2f-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

