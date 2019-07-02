---
title: Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumo: saiba como fazer backup e restaurar bancos de dados persistentes do servidor de chat no Skype for Business Server 2015.'
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417957"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="7ad1c-103">Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ad1c-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7ad1c-104">**Resumo:** Saiba como fazer backup e restaurar bancos de dados persistentes do servidor de chat no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7ad1c-105">O servidor de chat persistente exige que o software de banco de dados do SQL Server armazene dados de sala de chat, como histórico e conteúdo, configuração, provisionamento de usuário e outros metadados relevantes.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="7ad1c-106">Além disso, se a sua organização tiver regulamentos que exijam que a atividade de chat persistente seja arquivada, e o serviço de conformidade opcional estiver habilitado, o software de banco de dados do SQL Server será usado para armazenar dados de conformidade, incluindo conteúdo e eventos de chat, como ingressar e sair de salas.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="7ad1c-107">Conteúdo da sala de chat é armazenado no banco de dados de chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="7ad1c-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="7ad1c-108">Os dados de Conformidade são armazenados no banco de dados de Conformidade (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="7ad1c-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="7ad1c-109">Esses dados são essenciais para os negócios, cujo backup deve ser feito regularmente.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7ad1c-110">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7ad1c-111">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="7ad1c-112">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="7ad1c-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7ad1c-113">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="7ad1c-114">Fazer backup dos bancos de dados</span><span class="sxs-lookup"><span data-stu-id="7ad1c-114">Back up the databases</span></span>

<span data-ttu-id="7ad1c-115">Há duas maneiras de fazer backup de dados de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="7ad1c-116">Backup do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ad1c-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="7ad1c-117">O cmdlet **Export-CsPersistentChatData** , que exporta dados de chat persistentes como um arquivo</span><span class="sxs-lookup"><span data-stu-id="7ad1c-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="7ad1c-118">Dados criados usando o backup do SQL Server requerem espaço em disco significativamente maior – possivelmente 20 vezes maior – que os dados criados pelo **Export-CsPersistentChatData**, mas o backup do SQL Server é o procedimento com o qual os administradores provavelmente já estão familiarizados.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="7ad1c-119">Se você quiser usar os procedimentos de backup do SQL Server, consulte a documentação do SQL para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="7ad1c-120">Se quiser usar o cmdlet **Export-CsPersistentChatData**, você pode especificar o comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="7ad1c-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="7ad1c-121">ou</span><span class="sxs-lookup"><span data-stu-id="7ad1c-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="7ad1c-p103">Por exemplo, o seguinte comando exporta dados de Chat Persistente do banco de dados de Chat Persistente localizado no servidor atl-sql-001.contoso.com; os dados exportados serão armazenados no arquivo C:\Logs\PersistentChatData.zip. Como o parâmetro Level não foi especificado, comando fará uma exportação completa das informações de Chat Persistente:</span><span class="sxs-lookup"><span data-stu-id="7ad1c-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="7ad1c-124">Restaurar os bancos de dados</span><span class="sxs-lookup"><span data-stu-id="7ad1c-124">Restore the databases</span></span>

<span data-ttu-id="7ad1c-125">A maneira como você restaura seus dados de chat persistentes depende do método usado para fazer o backup.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="7ad1c-126">Se você usou procedimentos de backup do SQL Server, então deve usar procedimentos de restauração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ad1c-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="7ad1c-127">Se você usou o cmdlet **Export-CsPersistentChatData** para fazer backup de dados de chat persistente, deve usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados:</span><span class="sxs-lookup"><span data-stu-id="7ad1c-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="7ad1c-128">ou</span><span class="sxs-lookup"><span data-stu-id="7ad1c-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
