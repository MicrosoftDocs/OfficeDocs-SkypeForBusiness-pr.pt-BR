---
title: 'Lync Server 2013: integração com o Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 917ffc5103617c04a989ec91043a68fcce9f0320
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498518"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="0f9c3-102">Integrar Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9c3-103">_**Última modificação do tópico:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="0f9c3-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="0f9c3-104">O Exchange e o Lync Server têm uma longa história de integração e compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="0f9c3-105">Essa integração é mais perceptível no respectivo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="0f9c3-106">Por exemplo, as informações de presença do Lync podem ser relatadas no Microsoft Outlook; da mesma forma, o Lync pode usar o calendário do Outlook para atualizar automaticamente essas informações de presença.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="0f9c3-107">(Por exemplo, o Lync pode alterar seu status para ocupado sempre que o calendário mostrar que você tem uma reunião agendada.) Embora você não precise executar o Exchange para executar o Lync Server (ou vice-versa), há pouca dúvida de que usar os dois produtos juntos epitomizes a definição do termo "melhor juntos".</span><span class="sxs-lookup"><span data-stu-id="0f9c3-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="0f9c3-108">Isso é especialmente verdadeiro com o lançamento do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="0f9c3-109">Além dos recursos, como Unificação de mensagens e IM e presença, que são encontrados no Microsoft Exchange Server 2010 e no Microsoft Lync Server 2010, as versões 2013 dos produtos de servidor incluem vários recursos novos.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="0f9c3-110">Eles incluem:</span><span class="sxs-lookup"><span data-stu-id="0f9c3-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="0f9c3-111">**Integração com arquivamento do Lync**.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="0f9c3-112">No Lync Server 2013 os administradores ainda têm a opção de ter as transcrições de mensagens instantâneas e webconferência arquivadas no SQL Server (da mesma forma que essas transcrições foram arquivadas no Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="0f9c3-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="0f9c3-113">Como alternativa, no entanto, os administradores podem optar por ter transcrições arquivadas no Exchange 2013, armazenando essas transcrições nas caixas de correio de usuários individuais da mesma maneira que o Exchange arquiva comunicações.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="0f9c3-114">Isso significa um único repositório para todas as suas comunicações eletrônicas (do Exchange e do Lync Server), o que torna muito mais fácil procurar e recuperar essas comunicações arquivadas, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="0f9c3-115">**Repositório de contatos unificado**.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-115">**Unified Contact Store**.</span></span> <span data-ttu-id="0f9c3-116">No Lync Server 2010, os usuários tinham que manter listas de contatos separadas no Outlook e no Lync; na verdade, para garantir que você tenha os mesmos contatos disponíveis em ambos os produtos que você precisava manter listas de contatos duplicadas, uma para o Outlook e outra para o Lync.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="0f9c3-117">Com o Lync Server 2013, no entanto, os contatos do usuário podem ser armazenados no Exchange 2013 e no repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="0f9c3-118">O uso de um único repositório de contato permite que os usuários mantenham apenas um conjunto de contatos, com o mesmo conjunto de contatos disponível no Lync 2013, Outlook 2013 e Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="0f9c3-119">**Agendamento de reunião do Lync do OWA**.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="0f9c3-120">Com a integração do Lync Server 2013 e do Exchange 2013, os usuários podem agendar reuniões do Lync do Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="0f9c3-121">**Fotos de alta resolução**.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-121">**High resolution photos**.</span></span> <span data-ttu-id="0f9c3-122">O Lync 2010 pode exibir apenas pequenas fotos de seus contatos; Isso ocorre porque essas fotos foram armazenadas no Active Directory e o Active Directory impõe uma limitação de tamanho de 48 pixels por 48 pixels em fotos armazenadas.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="0f9c3-123">Com o Lync Server 2013, no entanto, as fotos podem ser armazenadas no Microsoft Exchange; Isso permite fotos de alta resolução tão grandes quanto 648 pixels por 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="0f9c3-124">Como você pode esperar, o Lync 2013 foi atualizado para permitir a exibição dessas fotografias de alta resolução.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="0f9c3-125">Tenha em mente que esses novos recursos exigem o uso do Lync Server 2013 e do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0f9c3-126">Além disso, os usuários que desejam aproveitar totalmente esses novos recursos devem ter contas no Lync Server 2013 e no Exchange 2013, e devem usar as versões mais recentes do software cliente (por exemplo, Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="0f9c3-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="0f9c3-127">Por exemplo, o repositório unificado de contatos não está disponível para usuários que foram hospedados no Lync Server 2010; da mesma forma, fotos de alta resolução não podem ser exibidas no Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="0f9c3-128">Esta documentação fornece informações sobre a integração do Lync Server 2013 e do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="0f9c3-129">inclusive informações passo a passo sobre como habilitar novos recursos, como a integração do arquivamento e do repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="0f9c3-130">Esta documentação não aborda a instalação e configuração iniciais desses dois produtos.</span><span class="sxs-lookup"><span data-stu-id="0f9c3-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="0f9c3-131">Para obter detalhes sobre a implantação do Lync Server 2013, consulte o Lync Server 2013 Tech Center em [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) .</span><span class="sxs-lookup"><span data-stu-id="0f9c3-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="0f9c3-132">Para obter detalhes sobre a implantação do Exchange 2013, consulte o Exchange 2013 Tech Center em [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .</span><span class="sxs-lookup"><span data-stu-id="0f9c3-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f9c3-133">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0f9c3-133">In This Section</span></span>

[<span data-ttu-id="0f9c3-134">Pré-requisitos para a integração do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="0f9c3-135">Configurando aplicativos parceiros no Microsoft Lync Server 2013 e no Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="0f9c3-136">Configurando o Microsoft Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="0f9c3-137">Configurando o Microsoft SharePoint Server 2013 para pesquisar dados arquivados do Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="0f9c3-138">Configurando o Microsoft Lync Server 2013 para usar o repositório unificado de contatos</span><span class="sxs-lookup"><span data-stu-id="0f9c3-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="0f9c3-139">Configurando o uso de fotos de alta resolução no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="0f9c3-140">Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para o Microsoft Lync Server 2013 voice mail</span><span class="sxs-lookup"><span data-stu-id="0f9c3-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="0f9c3-141">Integrando o Microsoft Lync Server 2013 e o Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="0f9c3-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

