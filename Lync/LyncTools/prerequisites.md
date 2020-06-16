---
title: Pré-requisitos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d8f0ee6a50d40f938a9f2c6f731b0a4afa647ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="05e7e-102">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="05e7e-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05e7e-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="05e7e-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="05e7e-104">Há vários requisitos de configuração de hardware, software e sistema que você precisará para executar a ferramenta de estresse e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05e7e-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="05e7e-105">Requisitos de hardware do cliente</span><span class="sxs-lookup"><span data-stu-id="05e7e-105">Client Hardware Requirements</span></span>

<span data-ttu-id="05e7e-106">Para executar a ferramenta de estresse e desempenho do Lync Server 2013 em sua implantação do Lync Server 2013, para todos os usuários do 4.500 cuja carga você deseja simular, você precisará de pelo menos um computador dedicado que atenda aos seguintes requisitos mínimos de hardware:</span><span class="sxs-lookup"><span data-stu-id="05e7e-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="05e7e-107">adaptador de rede de 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="05e7e-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="05e7e-108">8 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="05e7e-108">8-GB ram</span></span>

  - <span data-ttu-id="05e7e-109">2 unidades de processamento central (CPUs) de núcleo dual</span><span class="sxs-lookup"><span data-stu-id="05e7e-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="05e7e-110">Requisitos de software do cliente</span><span class="sxs-lookup"><span data-stu-id="05e7e-110">Client Software Requirements</span></span>

<span data-ttu-id="05e7e-111">Para executar a ferramenta de estresse e desempenho do Lync Server 2013 em sua implantação do Lync Server 2013, os sistemas operacionais com suporte são:</span><span class="sxs-lookup"><span data-stu-id="05e7e-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="05e7e-112">Sistema operacional Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="05e7e-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="05e7e-113">Sistema operacional Windows Server 2008 (edição de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="05e7e-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="05e7e-114">O computador cliente deve atender aos seguintes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="05e7e-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="05e7e-115">Você deve ter o [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime instalado.</span><span class="sxs-lookup"><span data-stu-id="05e7e-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="05e7e-116">No Windows Server 2008/Windows Server 2012, o recurso experiência desktop deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="05e7e-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="05e7e-117">Você deve ter o [pacote redistribuível do Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64) instalado.</span><span class="sxs-lookup"><span data-stu-id="05e7e-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="05e7e-118">Uma implantação do Lync Server 2013 totalmente configurada.</span><span class="sxs-lookup"><span data-stu-id="05e7e-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="05e7e-119">Bibliotecas do Microsoft Unified Communications Managed API (UCMA) 4,0 estão incluídas no pacote de instalação, portanto, o UCMA não é necessário e não deve ser instalado em computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="05e7e-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="05e7e-120">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="05e7e-120">Configuration Requirements</span></span>

<span data-ttu-id="05e7e-121">Os computadores que executarão a ferramenta de estresse e desempenho do Lync Server 2013 devem ser configurados de acordo com os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="05e7e-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="05e7e-122">Você deve estar conectado como um membro do domínio ou do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="05e7e-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="05e7e-123">O Lync Server 2013 estresse e a ferramenta de desempenho (LyncPerfTool.exe) não podem ser executados em um computador que também está executando os componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05e7e-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="05e7e-124">Você deve executar a ferramenta de criação de usuário do Lync Server 2013 (UserProvisioningTool.exe) no servidor de front-end ou no servidor Standard Edition onde as contas de usuário residirão.</span><span class="sxs-lookup"><span data-stu-id="05e7e-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="05e7e-125">Quando a ferramenta é executada várias vezes, cada usuário habilitado para a comunicação unificada da Microsoft deve ter um número de telefone exclusivo.</span><span class="sxs-lookup"><span data-stu-id="05e7e-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="05e7e-126">O tamanho do arquivo da página deve ser gerenciado pelo sistema ou deve ser pelo menos 1,5 vezes a quantidade de RAM no sistema.</span><span class="sxs-lookup"><span data-stu-id="05e7e-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

