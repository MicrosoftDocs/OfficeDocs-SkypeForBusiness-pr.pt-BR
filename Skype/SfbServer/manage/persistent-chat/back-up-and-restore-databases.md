---
title: Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Resumo: Saiba como fazer backup e restaurar bancos de dados do servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="76d88-103">Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="76d88-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="76d88-104">**Resumo:** Saiba como fazer backup e restaurar bancos de dados do servidor de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="76d88-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="76d88-105">Persistent Chat Server requer o software de banco de dados do SQL Server para armazenar dados de sala de chat, histórico e conteúdo, configuração, provisionamento de usuário e outros metadados relevantes.</span><span class="sxs-lookup"><span data-stu-id="76d88-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="76d88-106">Além disso, se sua organização tem as normas que exigem a atividade de Chat persistente para serem arquivados e o serviço opcional de conformidade está habilitado, o software de banco de dados do SQL Server é usado para armazenar dados de conformidade, incluindo o conteúdo de bate-papo e eventos, como ingressando e deixando salas.</span><span class="sxs-lookup"><span data-stu-id="76d88-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="76d88-107">Conteúdo da sala de bate-papo é armazenado no banco de Chat persistente (mgc).</span><span class="sxs-lookup"><span data-stu-id="76d88-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="76d88-108">Os dados de Conformidade são armazenados no banco de dados de Conformidade (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="76d88-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="76d88-109">Esses dados são essenciais para os negócios, cujo backup deve ser feito regularmente.</span><span class="sxs-lookup"><span data-stu-id="76d88-109">This is business-critical data that should be backed up regularly.</span></span> 
  
## <a name="back-up-the-databases"></a><span data-ttu-id="76d88-110">Fazer backup dos bancos de dados</span><span class="sxs-lookup"><span data-stu-id="76d88-110">Back up the databases</span></span>

<span data-ttu-id="76d88-111">Existem duas maneiras de fazer backup de dados de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="76d88-111">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="76d88-112">Backup do SQL Server</span><span class="sxs-lookup"><span data-stu-id="76d88-112">SQL Server Backup</span></span>
    
- <span data-ttu-id="76d88-113">O cmdlet **Export-CsPersistentChatData** , qual exporta os dados de Chat persistente como um arquivo</span><span class="sxs-lookup"><span data-stu-id="76d88-113">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="76d88-114">Dados criados usando o backup do SQL Server requerem espaço em disco significativamente maior – possivelmente 20 vezes maior – que os dados criados pelo **Export-CsPersistentChatData**, mas o backup do SQL Server é o procedimento com o qual os administradores provavelmente já estão familiarizados.</span><span class="sxs-lookup"><span data-stu-id="76d88-114">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="76d88-115">Se você quiser usar os procedimentos de backup do SQL Server, consulte a documentação do SQL para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="76d88-115">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="76d88-116">Se quiser usar o cmdlet **Export-CsPersistentChatData**, você pode especificar o comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="76d88-116">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="76d88-117">ou</span><span class="sxs-lookup"><span data-stu-id="76d88-117">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="76d88-p102">Por exemplo, o seguinte comando exporta dados de Chat Persistente do banco de dados de Chat Persistente localizado no servidor atl-sql-001.contoso.com; os dados exportados serão armazenados no arquivo C:\Logs\PersistentChatData.zip. Como o parâmetro Level não foi especificado, comando fará uma exportação completa das informações de Chat Persistente:</span><span class="sxs-lookup"><span data-stu-id="76d88-p102">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="76d88-120">Restaurar os bancos de dados</span><span class="sxs-lookup"><span data-stu-id="76d88-120">Restore the databases</span></span>

<span data-ttu-id="76d88-121">Como você restaura seus dados de Chat persistente depende do método que você usou para fazer o backup.</span><span class="sxs-lookup"><span data-stu-id="76d88-121">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="76d88-122">Se você usou procedimentos de backup do SQL Server, então deve usar procedimentos de restauração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76d88-122">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="76d88-123">Se você usou o cmdlet **Export-CsPersistentChatData** para fazer backup de dados de Chat persistente, você deve usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados:</span><span class="sxs-lookup"><span data-stu-id="76d88-123">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="76d88-124">ou</span><span class="sxs-lookup"><span data-stu-id="76d88-124">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


