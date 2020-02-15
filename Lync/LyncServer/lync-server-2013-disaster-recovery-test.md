---
title: 'Lync Server 2013: teste de recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc04381e315375fe0d5858c9a12ad577f6c8baf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="88a68-102">Teste de recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a68-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88a68-103">_**Última modificação do tópico:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="88a68-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="88a68-104">Execute uma recuperação do sistema para um servidor de pool do Lync Server 2013 para testar o processo de recuperação de desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="88a68-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="88a68-105">Este teste simulará uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, planos e dados estejam disponíveis para recuperação.</span><span class="sxs-lookup"><span data-stu-id="88a68-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="88a68-106">Tente girar o foco do teste a cada mês para que sua organização teste a falha de um servidor diferente ou outra parte do equipamento a cada vez.</span><span class="sxs-lookup"><span data-stu-id="88a68-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="88a68-107">Observe que a programação em que as organizações realizam testes de recuperação de desastres vai variar.</span><span class="sxs-lookup"><span data-stu-id="88a68-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="88a68-108">É muito importante que o teste de recuperação de desastres não seja ignorado ou inativo.</span><span class="sxs-lookup"><span data-stu-id="88a68-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="88a68-109">Exporte sua topologia do Lync Server 2013, políticas e definições de configuração para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="88a68-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="88a68-110">Entre outras coisas, esse arquivo pode ser usado para restaurar essas informações para o repositório de gerenciamento central após uma atualização, uma falha de hardware ou algum outro problema resultou em perda de dados.</span><span class="sxs-lookup"><span data-stu-id="88a68-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="88a68-111">Importe a topologia do Lync Server 2013, políticas e definições de configuração para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="88a68-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="88a68-112">Para fazer backup dos dados de produção do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="88a68-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="88a68-113">Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup do SQL Server padrão para despejar o banco de dados para um dispositivo de despejo de arquivo ou fita.</span><span class="sxs-lookup"><span data-stu-id="88a68-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="88a68-114">Use aplicativos de backup de terceiros para fazer o backup dos dados em um arquivo ou em uma fita.</span><span class="sxs-lookup"><span data-stu-id="88a68-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="88a68-115">Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.</span><span class="sxs-lookup"><span data-stu-id="88a68-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="88a68-116">Use o backup do sistema de arquivos ou terceiros para fazer o backup de conteúdo da reunião e logs de conformidade.</span><span class="sxs-lookup"><span data-stu-id="88a68-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="88a68-117">Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88a68-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="88a68-118">A primeira etapa do procedimento de failover inclui uma movimentação forçada de usuários do pool de produção para o pool de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="88a68-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="88a68-119">Este será um movimento forçado porque o pool de produção não estará disponível para aceitar a realocação do usuário.</span><span class="sxs-lookup"><span data-stu-id="88a68-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="88a68-120">O processo de movimentação de usuário do Lync Server 2013 é efetivamente uma alteração para um atributo no objeto da conta de usuário, além de uma atualização de registro no banco de dados SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="88a68-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="88a68-121">Esses dados podem ser restaurados por meio dos dois processos a seguir:</span><span class="sxs-lookup"><span data-stu-id="88a68-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="88a68-122">O banco de dados RTC pode ser restaurado a partir do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server, ou usando um utilitário de backup/restauração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="88a68-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="88a68-123">Os dados de contato do usuário podem ser restaurados com o utilitário DBIMPEXP. exe usando o arquivo XML que foi criado a partir da exportação do SQL Server de produção.</span><span class="sxs-lookup"><span data-stu-id="88a68-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="88a68-124">Após a restauração desses dados, os usuários podem se conectar efetivamente ao pool de recuperação de desastres do Lync Server 2013 e operar como de costume.</span><span class="sxs-lookup"><span data-stu-id="88a68-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="88a68-125">Para permitir que os usuários se conectem ao pool de recuperação de desastres do Lync Server 2013, será necessária uma alteração de registro DNS.</span><span class="sxs-lookup"><span data-stu-id="88a68-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="88a68-126">O pool de produção do Lync Server 2013 será referenciado por clientes que usam a configuração automática e os registros SRV DNS de:</span><span class="sxs-lookup"><span data-stu-id="88a68-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="88a68-127">SRV: \_SIP. \_TLS. \<domínio\> /CNAME: SIP. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="88a68-128">CNAME: SIP. \<domínio\> /CVC-pool-1. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="88a68-129">Para facilitar o failover, esse registro CNAME deve ser atualizado para fazer referência ao FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="88a68-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="88a68-130">CNAME: SIP. \<domínio\> /DROCSPool. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="88a68-131">SIP. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="88a68-132">AV.\<Domain\></span><span class="sxs-lookup"><span data-stu-id="88a68-132">AV.\<domain\></span></span>

  - <span data-ttu-id="88a68-133">webconf. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="88a68-134">OCSServices. \<domínio\></span><span class="sxs-lookup"><span data-stu-id="88a68-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88a68-135">Para obter procedimentos detalhados de administração e gerenciamento, consulte <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">fazendo backup e restaurando o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="88a68-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88a68-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="88a68-136">See Also</span></span>


[<span data-ttu-id="88a68-137">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a68-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="88a68-138">Cmdlets de backup e alta disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a68-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="88a68-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="88a68-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="88a68-140">Fazendo backup e restaurando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a68-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="88a68-141">Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a68-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

