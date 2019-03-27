---
title: Recuperação de desastres testes no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Executar uma recuperação do sistema para um Skype para o pool de servidores Business Server testar seu processo de recuperação de desastres documentadas
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884961"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="a12b3-103">Recuperação de desastres testes no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a12b3-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="a12b3-104">Execute uma recuperação do sistema para um Skype para o pool de servidores Business Server testar seu processo de recuperação de desastres documentadas.</span><span class="sxs-lookup"><span data-stu-id="a12b3-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="a12b3-105">Esse teste será simular uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, os planos e os dados estão disponíveis para a recuperação.</span><span class="sxs-lookup"><span data-stu-id="a12b3-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="a12b3-106">Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento.</span><span class="sxs-lookup"><span data-stu-id="a12b3-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="a12b3-p102">Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado.</span><span class="sxs-lookup"><span data-stu-id="a12b3-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="a12b3-109">Exporte seu Skype para Business Server topologia, políticas e definições de configuração para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a12b3-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="a12b3-110">O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.</span><span class="sxs-lookup"><span data-stu-id="a12b3-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="a12b3-111">Importe sua Skype para topologia de servidor de negócios, políticas e definições de configuração para o repositório de gerenciamento Central ou no computador local, conforme mostrado nos comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="a12b3-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="a12b3-112">Para fazer backup dos dados de produção:</span><span class="sxs-lookup"><span data-stu-id="a12b3-112">To back up production data:</span></span>

- <span data-ttu-id="a12b3-113">Fazer backup de bancos de dados RTC e LCSLog usando o SQL Server standard backup processo para o banco de dados para um dispositivo de despejo fita ou arquivo de despejo.</span><span class="sxs-lookup"><span data-stu-id="a12b3-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="a12b3-114">Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.</span><span class="sxs-lookup"><span data-stu-id="a12b3-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="a12b3-115">Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.</span><span class="sxs-lookup"><span data-stu-id="a12b3-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="a12b3-116">Use o backup do sistema de arquivos ou o backup de terceiros para fazer backup de logs de conteúdo e de conformidade da reunião.</span><span class="sxs-lookup"><span data-stu-id="a12b3-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="a12b3-117">Use a ferramenta de linha de comando de Export-CsConfiguration para fazer o backup Skype pelas configurações do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a12b3-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="a12b3-118">A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre.</span><span class="sxs-lookup"><span data-stu-id="a12b3-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="a12b3-119">O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.</span><span class="sxs-lookup"><span data-stu-id="a12b3-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="a12b3-120">O Skype para o processo de movimentação de Business Server do usuário é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados RTC SQL.</span><span class="sxs-lookup"><span data-stu-id="a12b3-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="a12b3-121">Esses dados podem ser restaurados do dispositivo despejo backup original da produção do SQL Server usando o processo de restauração do SQL Server standard, ou usando um terceiro backup/restauração utilitário.</span><span class="sxs-lookup"><span data-stu-id="a12b3-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="a12b3-122">Depois que esses dados for restaurados, os usuários efetivamente podem conectar ao pool de recuperação de desastres e operar como de costume.</span><span class="sxs-lookup"><span data-stu-id="a12b3-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="a12b3-123">Para permitir que os usuários se conectem ao pool de recuperação de desastres, uma alteração de registro de DNS será necessária.</span><span class="sxs-lookup"><span data-stu-id="a12b3-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="a12b3-124">A produção Skype para pool de negócios será referenciada pelos clientes estão usando a configuração automática e registros SRV de DNS:</span><span class="sxs-lookup"><span data-stu-id="a12b3-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="a12b3-125">SRV: _sip._tls. \<domain> /CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="a12b3-126">CNAME: SIP. \<domain> /cvc-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="a12b3-127">Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="a12b3-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="a12b3-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="a12b3-129">/ DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="a12b3-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-130">Sip.\<domain></span></span>
- <span data-ttu-id="a12b3-131">Antivírus.\<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-131">AV.\<domain></span></span>
- <span data-ttu-id="a12b3-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="a12b3-132">webconf.\<domain></span></span>
