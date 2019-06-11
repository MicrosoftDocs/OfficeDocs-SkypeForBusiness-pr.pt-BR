---
title: 'Lync Server 2013: Teste de recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="43d54-102">Teste de recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d54-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43d54-103">_**Tópico da última modificação:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="43d54-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="43d54-104">Realize uma recuperação do sistema para um servidor de pool do Lync Server 2013 para testar o processo de recuperação de desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="43d54-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="43d54-105">Esse teste simulará uma falha completa de hardware de um servidor e ajudará a garantir que os recursos, os planos e os dados estejam disponíveis para recuperação.</span><span class="sxs-lookup"><span data-stu-id="43d54-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="43d54-106">Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento.</span><span class="sxs-lookup"><span data-stu-id="43d54-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="43d54-p102">Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado.</span><span class="sxs-lookup"><span data-stu-id="43d54-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="43d54-109">Exportar a topologia, as políticas e as configurações de configuração do Lync Server 2013 para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="43d54-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="43d54-110">O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.</span><span class="sxs-lookup"><span data-stu-id="43d54-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="43d54-111">Importe as configurações de topologia, políticas e configuração do Lync Server 2013 para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="43d54-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="43d54-112">Para fazer backup de dados de produção do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="43d54-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="43d54-113">Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um dispositivo de despejo de arquivo ou fita.</span><span class="sxs-lookup"><span data-stu-id="43d54-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="43d54-114">Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.</span><span class="sxs-lookup"><span data-stu-id="43d54-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="43d54-115">Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.</span><span class="sxs-lookup"><span data-stu-id="43d54-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="43d54-116">Use o backup do sistema de arquivos ou de terceiros para fazer backup do conteúdo de reuniões e de logs de conformidade.</span><span class="sxs-lookup"><span data-stu-id="43d54-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="43d54-117">Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43d54-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="43d54-118">A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre.</span><span class="sxs-lookup"><span data-stu-id="43d54-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="43d54-119">O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.</span><span class="sxs-lookup"><span data-stu-id="43d54-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="43d54-120">O processo de transferência de usuário do Lync Server 2013 é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados SQL do RTC.</span><span class="sxs-lookup"><span data-stu-id="43d54-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="43d54-121">Esses dados podem ser restaurados por meio destes dois processos:</span><span class="sxs-lookup"><span data-stu-id="43d54-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="43d54-122">O banco de dados RTC pode ser restaurado do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="43d54-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="43d54-123">Os dados de contato do usuário podem ser restaurados por meio do utilitário DBIMPEXP.exe, usando o arquivo XML criado a partir da exportação do SQL Server de produção.</span><span class="sxs-lookup"><span data-stu-id="43d54-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="43d54-124">Depois que esses dados são restaurados, os usuários podem se conectar efetivamente ao pool de recuperação de desastres do Lync Server 2013 e operar normalmente.</span><span class="sxs-lookup"><span data-stu-id="43d54-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="43d54-125">Para permitir que os usuários se conectem ao pool de recuperação de desastres do Lync Server 2013, será necessário alterar um registro de DNS.</span><span class="sxs-lookup"><span data-stu-id="43d54-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="43d54-126">O pool de produção do Lync Server 2013 será referenciado por clientes que usam os registros de configuração automática e SRV DNS de:</span><span class="sxs-lookup"><span data-stu-id="43d54-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="43d54-127">SRV: \_SIP. \_TLS. \</CNAME\> de domínio: SIP. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="43d54-128">CNAME: SIP. \</CVC-pool-1.\> de domínio \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="43d54-129">Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="43d54-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="43d54-130">CNAME: SIP. \</DROCSPool.\> de domínio \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="43d54-131">SPI. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="43d54-132">AV.\<Domain\></span><span class="sxs-lookup"><span data-stu-id="43d54-132">AV.\<domain\></span></span>

  - <span data-ttu-id="43d54-133">webconf. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="43d54-134">OCSServices. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="43d54-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43d54-135">Para obter procedimentos detalhados de administração e gerenciamento, confira <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e restauração do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43d54-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43d54-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="43d54-136">See Also</span></span>


[<span data-ttu-id="43d54-137">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d54-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="43d54-138">Cmdlets de backup e alta disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d54-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="43d54-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="43d54-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="43d54-140">Fazer backup e restaurar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d54-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="43d54-141">Gerenciando recuperação de desastre, alta disponibilidade e Serviço de Backup do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d54-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

