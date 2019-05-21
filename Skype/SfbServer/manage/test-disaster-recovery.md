---
title: Teste de recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Executar uma recuperação do sistema para um servidor do pool do servidor do Skype for Business para testar o processo de recuperação de desastres documentado
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279211"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="b5486-103">Teste de recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b5486-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="b5486-104">Realize uma recuperação do sistema para um servidor do pool do servidor do Skype for Business para testar o processo de recuperação de desastres documentado.</span><span class="sxs-lookup"><span data-stu-id="b5486-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="b5486-105">Esse teste simulará uma falha de hardware completa para um servidor e ajudará a garantir que os recursos, planos e dados estejam disponíveis para recuperação.</span><span class="sxs-lookup"><span data-stu-id="b5486-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="b5486-106">Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento.</span><span class="sxs-lookup"><span data-stu-id="b5486-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="b5486-p102">Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado.</span><span class="sxs-lookup"><span data-stu-id="b5486-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="b5486-109">Exportar a topologia, as políticas e as configurações de configuração do Skype for Business Server para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b5486-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="b5486-110">O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.</span><span class="sxs-lookup"><span data-stu-id="b5486-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="b5486-111">Importe as configurações de topologia, políticas e configuração do Skype for Business Server para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="b5486-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="b5486-112">Para fazer backup de dados de produção:</span><span class="sxs-lookup"><span data-stu-id="b5486-112">To back up production data:</span></span>

- <span data-ttu-id="b5486-113">Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um dispositivo de despejo de arquivo ou fita.</span><span class="sxs-lookup"><span data-stu-id="b5486-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="b5486-114">Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.</span><span class="sxs-lookup"><span data-stu-id="b5486-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="b5486-115">Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.</span><span class="sxs-lookup"><span data-stu-id="b5486-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="b5486-116">Use o backup do sistema de arquivos ou backup de terceiros para fazer backup de conteúdo da reunião e registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b5486-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="b5486-117">Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b5486-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="b5486-118">A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre.</span><span class="sxs-lookup"><span data-stu-id="b5486-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="b5486-119">O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5486-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="b5486-120">O processo de mudança de usuário do Skype for Business Server é efetivamente uma mudança para um atributo no objeto da conta de usuário, além de uma atualização de registro no banco de dados SQL do RTC.</span><span class="sxs-lookup"><span data-stu-id="b5486-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="b5486-121">Esses dados podem ser restaurados do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b5486-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="b5486-122">Depois que esses dados são restaurados, os usuários podem conectar-se efetivamente ao pool de recuperação de desastres e operar normalmente.</span><span class="sxs-lookup"><span data-stu-id="b5486-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="b5486-123">Para permitir que os usuários se conectem ao pool de recuperação de desastre, uma alteração de registro DNS será necessária.</span><span class="sxs-lookup"><span data-stu-id="b5486-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="b5486-124">O pool de produção do Skype for Business será referenciado por clientes que usam os registros de configuração automática e SRV DNS de:</span><span class="sxs-lookup"><span data-stu-id="b5486-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="b5486-125">SRV: _sip. _tls. \<domain>/CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="b5486-126">CNAME: SIP. \<domain>/CVC-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="b5486-127">Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="b5486-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="b5486-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="b5486-129">/DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="b5486-130">SPI. \<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-130">Sip.\<domain></span></span>
- <span data-ttu-id="b5486-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-131">AV.\<domain></span></span>
- <span data-ttu-id="b5486-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="b5486-132">webconf.\<domain></span></span>
