---
title: Teste de recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Executar uma recuperação de sistema para um servidor de pool do Skype for Business Server para testar seu processo documentado de recuperação de desastres
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832811"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="7c070-103">Teste de recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c070-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="7c070-104">Execute uma recuperação de sistema para um servidor de pool do Skype for Business Server para testar seu processo documentado de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="7c070-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="7c070-105">Esse teste simula uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, planos e dados estão disponíveis para recuperação.</span><span class="sxs-lookup"><span data-stu-id="7c070-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="7c070-106">Tente girar o foco do teste a cada mês para que sua organização teste a falha de um servidor diferente ou de outro equipamento sempre.</span><span class="sxs-lookup"><span data-stu-id="7c070-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="7c070-107">Observe que o cronograma pelo qual as organizações executam testes de Recuperação de Desastre variará.</span><span class="sxs-lookup"><span data-stu-id="7c070-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="7c070-108">É muito importante que o teste de recuperação de desastres não seja ignorado ou ignorado.</span><span class="sxs-lookup"><span data-stu-id="7c070-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="7c070-109">Exporte a topologia, as políticas e as definições de configuração do Skype for Business Server para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="7c070-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="7c070-110">Entre outras coisas, esse arquivo pode ser usado para restaurar essas informações para o Armazenamento de Gerenciamento Central após uma atualização, uma falha de hardware ou algum outro problema que resulte em perda de dados.</span><span class="sxs-lookup"><span data-stu-id="7c070-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="7c070-111">Importe sua topologia, políticas e definições de configuração do Skype for Business Server para o armazenamento de Gerenciamento Central ou para o computador local, conforme mostrado nos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7c070-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="7c070-112">Para fazer o back up dos dados de produção:</span><span class="sxs-lookup"><span data-stu-id="7c070-112">To back up production data:</span></span>

- <span data-ttu-id="7c070-113">Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um arquivo ou dispositivo de despejo de fita.</span><span class="sxs-lookup"><span data-stu-id="7c070-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="7c070-114">Use o aplicativo de backup de terceiros para fazer backup dos dados em arquivos ou em fita.</span><span class="sxs-lookup"><span data-stu-id="7c070-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="7c070-115">Use o Export-CsUserData cmdlet para criar uma exportação XML de todo o banco de dados RTC.</span><span class="sxs-lookup"><span data-stu-id="7c070-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="7c070-116">Use o backup do sistema de arquivos ou backup de terceiros para fazer backup do conteúdo da reunião e dos logs de conformidade.</span><span class="sxs-lookup"><span data-stu-id="7c070-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="7c070-117">Use a Export-CsConfiguration de linha de comando para fazer o back up das configurações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c070-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="7c070-118">A primeira etapa do procedimento de failover inclui uma movimentação forçada de usuários do pool de produção para o pool de Recuperação de Desastres.</span><span class="sxs-lookup"><span data-stu-id="7c070-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="7c070-119">Isso será uma movimentação forçada porque o pool de produção não estará disponível para aceitar a realocação do usuário.</span><span class="sxs-lookup"><span data-stu-id="7c070-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="7c070-120">O processo de movimentação do usuário do Skype for Business Server é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="7c070-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="7c070-121">Esses dados podem ser restaurados do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7c070-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="7c070-122">Depois que esses dados são restaurados, os usuários podem se conectar efetivamente ao pool de Recuperação de Desastres e operar normalmente.</span><span class="sxs-lookup"><span data-stu-id="7c070-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="7c070-123">Para permitir que os usuários se conectem ao pool de Recuperação de Desastres, uma alteração de registro DNS será necessária.</span><span class="sxs-lookup"><span data-stu-id="7c070-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="7c070-124">O pool de produção do Skype for Business será referenciado pelos clientes usando a configuração automática e os registros SRV DNS de:</span><span class="sxs-lookup"><span data-stu-id="7c070-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="7c070-125">SRV: _sip._tls.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="7c070-126">/CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="7c070-127">CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="7c070-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="7c070-129">Para facilitar o failover, esse registro CNAME deve ser atualizado para fazer referência ao FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="7c070-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="7c070-130">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="7c070-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="7c070-132">Sip.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-132">Sip.\<domain></span></span>
- <span data-ttu-id="7c070-133">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-133">AV.\<domain></span></span>
- <span data-ttu-id="7c070-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="7c070-134">webconf.\<domain></span></span>
