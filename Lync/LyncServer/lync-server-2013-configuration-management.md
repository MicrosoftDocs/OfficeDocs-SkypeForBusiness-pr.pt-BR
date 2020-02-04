---
title: 'Lync Server 2013: gerenciamento de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6997f64695a4df606e6fbaa9767f22be04de6615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="c19a4-102">Gerenciamento de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c19a4-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c19a4-103">_**Tópico da última modificação:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c19a4-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="c19a4-104">Gerenciamento de configuração é o processo de gravação e acompanhamento de ativos de hardware e software e informações de configuração do sistema.</span><span class="sxs-lookup"><span data-stu-id="c19a4-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="c19a4-105">Geralmente, é usado para acompanhar licenças de software, manter uma compilação de hardware e software padrão para computadores e servidores cliente e definir padrões de nomenclatura para novos computadores.</span><span class="sxs-lookup"><span data-stu-id="c19a4-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="c19a4-106">O gerenciamento de configuração geralmente abrange as seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="c19a4-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="c19a4-107">**Hardware**   esta categoria controla os pedaços de equipamento que a organização de ti tem, onde o equipamento está localizado e quem usa equipamento.</span><span class="sxs-lookup"><span data-stu-id="c19a4-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="c19a4-108">Essas informações permitem que uma organização planeje e planeje atualizações, mantenha compilações de hardware padrão, informe o valor dos ativos de ti para fins contábeis e ajude a evitar roubo.</span><span class="sxs-lookup"><span data-stu-id="c19a4-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="c19a4-109">**Software**   essa categoria controla o software instalado em cada computador, os números de versão e o local em que as licenças são mantidas.</span><span class="sxs-lookup"><span data-stu-id="c19a4-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="c19a4-110">Essas informações ajudam a planejar atualizações, para garantir que o software seja licenciado e detectar a presença de softwares não autorizados (e não licenciados).</span><span class="sxs-lookup"><span data-stu-id="c19a4-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="c19a4-111">**Builds padrão esta**   categoria acompanha a compilação padrão atual para os computadores cliente e servidores e se os computadores cliente e servidores atendem a esse padrão.</span><span class="sxs-lookup"><span data-stu-id="c19a4-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="c19a4-112">Definir e aplicar construções padrão ajuda a equipe de suporte porque a equipe é necessária para manter apenas um número limitado de versões de cada parte do software.</span><span class="sxs-lookup"><span data-stu-id="c19a4-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="c19a4-113">**Hotfixes e atualizações cumulativas**   essa categoria controla quais service packs são testados e aprovados para uso e quais computadores estão atualizados.</span><span class="sxs-lookup"><span data-stu-id="c19a4-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="c19a4-114">Essas informações são importantes para reduzir o risco de que os computadores sejam comprometidos e para detectar os usuários que instalaram atualizações não aprovadas.</span><span class="sxs-lookup"><span data-stu-id="c19a4-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="c19a4-115">**Informações de configuração do sistema**   essa categoria acompanha a função de um sistema, a interação entre elementos do sistema e os processos que dependem de um sistema executando suavemente.</span><span class="sxs-lookup"><span data-stu-id="c19a4-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="c19a4-116">Por exemplo, um servidor proxy de terceiros pode ser configurado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="c19a4-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="c19a4-117">A dependência do servidor proxy neste servidor deve ser compreendida e os planos de contingência podem ser necessários se houver uma falha.</span><span class="sxs-lookup"><span data-stu-id="c19a4-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="c19a4-118">Se o servidor proxy puder ser configurado para também se comunicar com outro servidor front-end, as dependências e os planos de contingência provavelmente serão alterados.</span><span class="sxs-lookup"><span data-stu-id="c19a4-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="c19a4-119">Implementando o gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="c19a4-119">Implementing configuration management</span></span>

<span data-ttu-id="c19a4-120">Depois de determinar quais itens precisam gerenciar, implemente o gerenciamento de configuração coletando dados e dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="c19a4-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="c19a4-121">A abordagem mais simples para pequenas organizações é coletar dados manualmente (número e modelo de computadores cliente, sistema operacional, software instalado) e salvá-los em um documento do Office Word ou Office Excel.</span><span class="sxs-lookup"><span data-stu-id="c19a4-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="c19a4-122">Para sistemas maiores, mais complexos e em constante mudança, a descoberta de ativos e a coleta de informações detalhadas deve ser automatizada.</span><span class="sxs-lookup"><span data-stu-id="c19a4-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="c19a4-123">Decidir quais informações são relevantes para a sua organização e gravá-las em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c19a4-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="c19a4-124">O banco de dados de gerenciamento de configuração é uma ferramenta útil para a equipe de suporte e o gerenciamento nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="c19a4-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="c19a4-125">**Auditorias de segurança**   o banco de dados permite que você identifique os servidores que estão executando o Lync Server e sistemas de computador cliente que devem ter hotfixes aplicados ou que perderam a instalação de um Service Pack ou das atualizações mais recentes de antivírus.</span><span class="sxs-lookup"><span data-stu-id="c19a4-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="c19a4-126">**A instalação**   do software identificando versões do software cliente e controlando-as ajudará os administradores a planejar atualizações de versão e novas instalações e também ajudando com a documentação de licenciamento e a conformidade.</span><span class="sxs-lookup"><span data-stu-id="c19a4-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="c19a4-127">**Informações de configuração**   se você mantiver uma lista atualizada de todas as configurações que foram alteradas do padrão, você poderá solucionar problemas de forma rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="c19a4-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="c19a4-128">**Planejando atualizações**   se uma avaliação de capacidade revelar que é necessário espaço de armazenamento adicional nos seus servidores de banco de dados do Lync, é importante saber se cada servidor tem um controlador RAID interno.</span><span class="sxs-lookup"><span data-stu-id="c19a4-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="c19a4-129">Em caso afirmativo, eles são o mesmo modelo?</span><span class="sxs-lookup"><span data-stu-id="c19a4-129">If they do, then are they the same model?</span></span> <span data-ttu-id="c19a4-130">Eles têm o mesmo número de discos instalados?</span><span class="sxs-lookup"><span data-stu-id="c19a4-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="c19a4-131">O banco de dados de gerenciamento de configuração indicará o tipo de disco que pode ser instalado, o número e o caminho de atualização em cada caso.</span><span class="sxs-lookup"><span data-stu-id="c19a4-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="c19a4-132">Ferramentas usadas para gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="c19a4-132">Tools used for configuration management</span></span>

<span data-ttu-id="c19a4-133">Há muitas ferramentas para detectar, auditar e relatar ativos.</span><span class="sxs-lookup"><span data-stu-id="c19a4-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="c19a4-134">Algumas dessas ferramentas são discutidas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c19a4-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="c19a4-135">**Scripts automatizados**   você pode escrever scripts simples para relatar itens como o sistema operacional, o nível do Service Pack e se existe um software em um conjunto específico de computadores.</span><span class="sxs-lookup"><span data-stu-id="c19a4-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="c19a4-136">Você pode escrever esses scripts para os requisitos exatos de uma organização.</span><span class="sxs-lookup"><span data-stu-id="c19a4-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="c19a4-137">No entanto, o número necessário de scripts e sua complexidade pode fazer com que os scripts criem e mantenham seus custos caros.</span><span class="sxs-lookup"><span data-stu-id="c19a4-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="c19a4-138">**Ferramentas automatizadas**   dependendo do tamanho da sua empresa e de suas necessidades organizacionais, você pode querer considerar o uso de ferramentas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="c19a4-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="c19a4-139">Ferramentas como o Microsoft Endpoint Configuration Manager incorporam modelos de relatório padrão (como o nível de Service Pack) e também permitem que você crie relatórios personalizados, por exemplo, para um aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c19a4-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="c19a4-140">O Microsoft Endpoint Configuration Manager também pode ser usado para relatar configurações de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="c19a4-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="c19a4-141">Relação com gerenciamento de alterações</span><span class="sxs-lookup"><span data-stu-id="c19a4-141">Relationship with change management</span></span>

<span data-ttu-id="c19a4-142">O gerenciamento de configuração está intimamente relacionado ao gerenciamento de alterações.</span><span class="sxs-lookup"><span data-stu-id="c19a4-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="c19a4-143">O gerenciamento de configuração identifica a necessidade de alteração e identifica e registra a ocorrência de uma alteração.</span><span class="sxs-lookup"><span data-stu-id="c19a4-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="c19a4-144">Por exemplo, o banco de dados de gerenciamento de configuração pode ser usado para identificar os servidores que exigem um hotfix.</span><span class="sxs-lookup"><span data-stu-id="c19a4-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="c19a4-145">O gerenciamento de alterações define o processo para aplicar o hotfix.</span><span class="sxs-lookup"><span data-stu-id="c19a4-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="c19a4-146">Por outro lado, se uma nova atualização cumulativa for implementada, o processo de gerenciamento de alterações deverá fornecer essas informações para o sistema de gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="c19a4-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="c19a4-147">As ferramentas de gerenciamento de configuração provavelmente precisarão ser configuradas para identificar o novo software, para que eles possam descobrir e controlar onde e quando o software é implantado.</span><span class="sxs-lookup"><span data-stu-id="c19a4-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

