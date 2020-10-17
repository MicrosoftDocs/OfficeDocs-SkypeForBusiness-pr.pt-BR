---
title: 'Lync Server 2013: visão geral do analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dd3cda0375c7c7e9d15f2ecd31b47a1dee587c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530718"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="f61bb-102">Visão geral do Best Practices Analyzer no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f61bb-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f61bb-103">_**Última modificação do tópico:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="f61bb-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="f61bb-104">Você pode usar o Lync Server 2013, o analisador de práticas recomendadas para identificar e resolver problemas com a sua implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="f61bb-105">O Lync Server 2013, Best Practices Analyzer coleta informações de configuração dos componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="f61bb-106">Com o acesso à rede apropriado, o analisador de práticas recomendadas pode examinar servidores que executam os serviços de domínio do Active Directory, a Unificação de mensagens (UM) do Exchange Server e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="f61bb-107">É possível usar o Analisador de Prática Recomendada para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f61bb-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="f61bb-108">Realize proativamente verificações, analisando se a configuração está definida de acordo com as práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="f61bb-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="f61bb-109">Detectar automaticamente as atualizações necessárias para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="f61bb-110">Gerar uma lista de problemas, como as definições de configuração inadequadas, opções não suportadas, atualizações ausentes ou práticas não recomendadas.</span><span class="sxs-lookup"><span data-stu-id="f61bb-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="f61bb-111">Ajuda para resolver problema e corrigir problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="f61bb-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="f61bb-112">O Analisador de Prática Recomendada oferece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="f61bb-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="f61bb-113">Pré-requisitos de instalação mínimos.</span><span class="sxs-lookup"><span data-stu-id="f61bb-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="f61bb-114">Documentação online sobre problemas relatados, incluindo dicas de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="f61bb-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="f61bb-115">Informação de configuração que você pode salvar para revisão posterior.</span><span class="sxs-lookup"><span data-stu-id="f61bb-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="f61bb-116">Análise do sistema de tecnologia de ponta.</span><span class="sxs-lookup"><span data-stu-id="f61bb-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="f61bb-117">O Best Practices Analyzer usa um conjunto de arquivos de configuração XML para determinar as informações a serem coletadas do seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="f61bb-118">Além de verificar os Serviços de Domínio do Active Directory, verifica as fontes como o registro do sistema operacional do Windows Server e as configurações no Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="f61bb-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="f61bb-119">O Best Practices Analyzer compara os dados que coleta com um conjunto de regras predefinidas para as configurações e configurações das implantações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="f61bb-120">Após comparar os dados coletados com as regras pré-definidas, a ferramenta relata problemas.</span><span class="sxs-lookup"><span data-stu-id="f61bb-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="f61bb-121">Para cada problema que ele relata, o analisador de práticas recomendadas fornece informações sobre o que foi encontrado no ambiente verificado do Lync Server 2013 e a configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="f61bb-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="f61bb-122">O Analisador de Prática Recomendada também oferece links para informações mais detalhadas sobre problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="f61bb-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f61bb-123">O Lync Server 2013, Best Practices Analyzer coleta informações de configuração somente dos componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f61bb-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="f61bb-124">É possível usar versões anteriores da ferramenta para verificar ambientes anteriores.</span><span class="sxs-lookup"><span data-stu-id="f61bb-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="f61bb-125">Para obter detalhes, consulte <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f61bb-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

