---
title: 'Lync Server 2013: visão geral do analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a304f33071b8be13c61c3f930f196113ac3af6de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="85cbc-102">Visão geral do analisador de práticas recomendadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85cbc-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85cbc-103">_**Tópico da última modificação:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="85cbc-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="85cbc-104">Você pode usar o Lync Server 2013, o analisador de práticas recomendadas para identificar e resolver problemas com a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="85cbc-105">O Lync Server 2013, o analisador de práticas recomendadas coleta informações de configuração dos componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="85cbc-106">Com o acesso à rede adequado, o analisador de práticas recomendadas pode examinar servidores que executam os serviços de domínio do Active Directory, o Exchange Server Unified Messaging (UM) e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="85cbc-107">Você pode usar o analisador de práticas recomendadas para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="85cbc-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="85cbc-108">Fazer verificações proativas, verificando se a configuração está definida de acordo com as práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="85cbc-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="85cbc-109">Detectar automaticamente as atualizações necessárias ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="85cbc-110">Gere uma lista de problemas, como configurações de configuração otimizadas, opções sem suporte, atualizações ausentes ou práticas que não recomendamos.</span><span class="sxs-lookup"><span data-stu-id="85cbc-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="85cbc-111">Ajudar você a solucionar problemas e corrigir problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="85cbc-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="85cbc-112">O analisador de práticas recomendadas oferece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="85cbc-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="85cbc-113">Pré-requisitos mínimos de instalação.</span><span class="sxs-lookup"><span data-stu-id="85cbc-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="85cbc-114">Documentação online sobre problemas relatados, incluindo dicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="85cbc-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="85cbc-115">Informações de configuração que você pode salvar para ver mais tarde.</span><span class="sxs-lookup"><span data-stu-id="85cbc-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="85cbc-116">Análise do sistema de ponta.</span><span class="sxs-lookup"><span data-stu-id="85cbc-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="85cbc-117">O analisador de práticas recomendadas usa um conjunto de arquivos de configuração XML para determinar as informações a serem coletadas do seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="85cbc-118">Além de verificar os serviços de domínio do Active Directory, ele verifica fontes como o registro do sistema operacional do Windows Server e as configurações na instrumentação de gerenciamento do Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="85cbc-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="85cbc-119">O analisador de práticas recomendadas compara os dados que coleta com um conjunto de regras predefinidas para as configurações e configurações das implantações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="85cbc-120">Após comparar os dados coletados com as regras predefinidas, a ferramenta relata problemas.</span><span class="sxs-lookup"><span data-stu-id="85cbc-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="85cbc-121">Para cada edição que ele relata, o analisador de práticas recomendadas fornece informações sobre o que foi encontrado no ambiente do Lync Server 2013 verificado e a configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="85cbc-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="85cbc-122">O analisador de práticas recomendadas também fornece links para informações mais detalhadas sobre os problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="85cbc-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85cbc-123">O Lync Server 2013, o analisador de práticas recomendadas coleta informações de configuração somente de componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85cbc-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="85cbc-124">Você pode usar as versões anteriores da ferramenta para verificar os ambientes anteriores.</span><span class="sxs-lookup"><span data-stu-id="85cbc-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="85cbc-125">Para obter detalhes, consulte <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">requisitos para a execução do analisador de práticas recomendadas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85cbc-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

