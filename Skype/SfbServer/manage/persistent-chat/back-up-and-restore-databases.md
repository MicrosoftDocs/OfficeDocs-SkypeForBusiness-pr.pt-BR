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
description: 'Resumo: saiba como fazer backup e restaurar bancos de dados do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: eb6b7e005691abda351993e716ba43a137ffa28c17f7fc9e6297a7e1373f9ad7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281704"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como fazer backup e restaurar bancos de dados do Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Servidor de Chat Persistente SQL Server software de banco de dados para armazenar dados da sala de chat, como histórico e conteúdo, configuração, provisionamento do usuário e outros metadados relevantes. Além disso, se sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada e o serviço de Conformidade opcional estiver habilitado, o software de banco de dados do SQL Server será usado para armazenar dados de conformidade, incluindo conteúdo de chat e eventos, como ingressar e sair de salas. O conteúdo da sala de chat é armazenado no banco de dados de Chat Persistente (mgc). Os dados de conformidade são armazenados no banco de dados de conformidade (mgccomp). Esses são dados críticos para os negócios que devem ser respaldados regularmente. 
  
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="back-up-the-databases"></a>Fazer o back up dos bancos de dados

Há duas maneiras de fazer o back up de dados de Chat Persistente. 
  
- SQL Server Backup
    
- O cmdlet **Export-CsPersistentChatData,** que exporta dados de Chat Persistente como um arquivo
    
Os dados criados usando o backup do SQL Server exigem significativamente mais espaço em disco , possivelmente 20 vezes mais do que os criados pelo cmdlet **Export-CsPersistentChatData,** mas o backup SQL Server provavelmente será um procedimento com o qual você está familiarizado.
  
Se você quiser usar SQL Server de backup, consulte sua documentação SQL para obter mais informações. 
  
Se você quiser usar o cmdlet **Export-CsPersistentChatData,** especifique o comando da seguinte forma:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

ou
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por exemplo, o comando a seguir exporta dados de Chat Persistente do banco de dados de Chat Persistente localizado no servidor atl-sql-001.contoso.com; os dados exportados serão armazenados no arquivo C:\Logs\PersistentChatData.zip. Como o parâmetro Level não foi especificado, o comando fará uma exportação completa das informações do Chat Persistente:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurar os bancos de dados

A forma como você restaura seus dados de Chat Persistente depende do método usado para fazer backup. Se você usou SQL Server de backup, deve usar SQL Server de restauração. Se você usou o cmdlet **Export-CsPersistentChatData** para fazer backup de dados de Chat Persistente, use o cmdlet **Import-CsPersistentChatData** para restaurar os dados:
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

ou
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
