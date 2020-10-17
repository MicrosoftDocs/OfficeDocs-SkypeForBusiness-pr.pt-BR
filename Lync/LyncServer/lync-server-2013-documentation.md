---
title: 'Lync Server 2013: documentação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2785391f93f2844809aaad06e4efff9c2e86505d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501168"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="a0e55-102">Documentação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0e55-102">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0e55-103">_**Última modificação do tópico:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a0e55-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a0e55-104">O modelo MOF é composto por muitas funções de gerenciamento de serviços.</span><span class="sxs-lookup"><span data-stu-id="a0e55-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="a0e55-105">A documentação sobre como e quando tarefas são executadas pode ser compartilhada com membros da mesma equipe ou com outras equipes.</span><span class="sxs-lookup"><span data-stu-id="a0e55-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="a0e55-106">O método de armazenamento e compartilhamento da documentação pode variar de acordo com o tipo de função.</span><span class="sxs-lookup"><span data-stu-id="a0e55-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="a0e55-107">Por exemplo, os procedimentos para administração do sistema podem ser armazenados como documentos do Word, pois eles provavelmente serão impressos e referenciados com frequência.</span><span class="sxs-lookup"><span data-stu-id="a0e55-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="a0e55-108">As informações de gerenciamento de configuração podem ser geradas e armazenadas automaticamente em um banco de dados para facilitar a pesquisa e indexação.</span><span class="sxs-lookup"><span data-stu-id="a0e55-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="a0e55-109">Algumas documentações podem ser confidenciais e devem ser restringidas.</span><span class="sxs-lookup"><span data-stu-id="a0e55-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="a0e55-110">Sistemas de gerenciamento de documentos</span><span class="sxs-lookup"><span data-stu-id="a0e55-110">Document management systems</span></span>

<span data-ttu-id="a0e55-111">Um sistema de gerenciamento de documentação atua como um repositório central para documentos e ajuda a garantir que apenas a revisão mais recente de um documento esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="a0e55-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="a0e55-112">Você também pode considerar o arquivamento da versão antiga do documento para referência.</span><span class="sxs-lookup"><span data-stu-id="a0e55-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="a0e55-113">O Lync Server fornece funcionalidade adequada para essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="a0e55-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a0e55-114">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="a0e55-114">Databases</span></span>

<span data-ttu-id="a0e55-115">Várias ferramentas e funções de gerenciamento foram discutidas que são adequadas para o uso de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a0e55-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="a0e55-116">O processo de gerenciamento de configuração provavelmente usará processos automatizados que armazenam grandes quantidades de dados que exigem indexação e pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a0e55-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="a0e55-117">A equipe de suporte pode pesquisar um banco de dados de problemas e resoluções anteriores ao solucionar novos problemas.</span><span class="sxs-lookup"><span data-stu-id="a0e55-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="a0e55-118">É provável que haja diferentes bancos de dados sendo usados para finalidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="a0e55-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="a0e55-119">Decida se esses bancos de dados devem ser vinculados ou combinados.</span><span class="sxs-lookup"><span data-stu-id="a0e55-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="a0e55-120">Por exemplo, se o Service Desk identificar vários problemas com um tema comum (como novo software causando um problema com um adaptador de rede específico), a equipe de suporte poderá consultar o banco de dados de configuração para prever quantos computadores podem ser afetados.</span><span class="sxs-lookup"><span data-stu-id="a0e55-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

