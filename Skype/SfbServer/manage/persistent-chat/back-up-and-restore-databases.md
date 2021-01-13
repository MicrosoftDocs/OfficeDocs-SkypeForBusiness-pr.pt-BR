---
title: Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumo: Saiba como fazer backup e restaurar bancos de dados do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826371"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="9ced0-103">Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9ced0-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9ced0-104">**Resumo:** Saiba como fazer backup e restaurar bancos de dados do Servidor de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9ced0-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9ced0-105">O Servidor de Chat Persistente requer o software de banco de dados do SQL Server para armazenar dados de sala de chat, como histórico e conteúdo, configuração, provisionamento do usuário e outros metadados relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ced0-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="9ced0-106">Além disso, se sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada e o serviço de Conformidade opcional estiver habilitado, o software de banco de dados do SQL Server será usado para armazenar dados de conformidade, incluindo conteúdo de chat e eventos, como ingressar e sair de salas.</span><span class="sxs-lookup"><span data-stu-id="9ced0-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="9ced0-107">O conteúdo da sala de chat é armazenado no banco de dados de Chat Persistente (mgc).</span><span class="sxs-lookup"><span data-stu-id="9ced0-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="9ced0-108">Os dados de conformidade são armazenados no banco de dados de Conformidade (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="9ced0-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="9ced0-109">Esses são dados críticos para os negócios que devem ser feito backup regularmente.</span><span class="sxs-lookup"><span data-stu-id="9ced0-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9ced0-110">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9ced0-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9ced0-111">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="9ced0-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="9ced0-112">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="9ced0-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9ced0-113">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9ced0-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="9ced0-114">Fazer o back up dos bancos de dados</span><span class="sxs-lookup"><span data-stu-id="9ced0-114">Back up the databases</span></span>

<span data-ttu-id="9ced0-115">Há duas maneiras de fazer o back up de dados de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="9ced0-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="9ced0-116">SQL Server Backup</span><span class="sxs-lookup"><span data-stu-id="9ced0-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="9ced0-117">O cmdlet **Export-CsPersistentChatData,** que exporta dados de Chat Persistente como um arquivo</span><span class="sxs-lookup"><span data-stu-id="9ced0-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="9ced0-118">Os dados criados com o uso do backup do SQL Server exigem significativamente mais espaço em disco , possivelmente 20 vezes mais, do que os criados pelo cmdlet **Export-CsPersistentChatData,** mas é provável que o backup do SQL Server seja um procedimento com o qual você está familiarizado.</span><span class="sxs-lookup"><span data-stu-id="9ced0-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="9ced0-119">Se você quiser usar procedimentos de backup do SQL Server, consulte a documentação do SQL para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9ced0-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="9ced0-120">Se você quiser usar o cmdlet **Export-CsPersistentChatData,** poderá especificar o comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9ced0-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="9ced0-121">ou</span><span class="sxs-lookup"><span data-stu-id="9ced0-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="9ced0-122">Por exemplo, o comando a seguir exporta dados de Chat Persistente do banco de dados de Chat Persistente localizado no servidor atl-sql-001.contoso.com; os dados exportados serão armazenados no arquivo C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="9ced0-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="9ced0-123">Como o parâmetro Level não foi especificado, o comando fará uma exportação completa das informações de Chat Persistente:</span><span class="sxs-lookup"><span data-stu-id="9ced0-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="9ced0-124">Restaurar os bancos de dados</span><span class="sxs-lookup"><span data-stu-id="9ced0-124">Restore the databases</span></span>

<span data-ttu-id="9ced0-125">A maneira como você restaura seus dados de Chat Persistente depende do método usado para fazer o backup.</span><span class="sxs-lookup"><span data-stu-id="9ced0-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="9ced0-126">Se você usou procedimentos de backup do SQL Server, deverá usar os procedimentos de restauração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ced0-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="9ced0-127">Se você usou o cmdlet **Export-CsPersistentChatData** para fazer backup de dados de Chat Persistente, deve usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados:</span><span class="sxs-lookup"><span data-stu-id="9ced0-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="9ced0-128">ou</span><span class="sxs-lookup"><span data-stu-id="9ced0-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
