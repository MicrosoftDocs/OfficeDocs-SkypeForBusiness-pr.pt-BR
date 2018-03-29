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
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Fazer backup e restaurar bancos de dados de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como fazer backup e restaurar bancos de dados do servidor de Chat persistente no Skype para Business Server 2015.
  
Persistent Chat Server requer o software de banco de dados do SQL Server para armazenar dados de sala de chat, histórico e conteúdo, configuração, provisionamento de usuário e outros metadados relevantes. Além disso, se sua organização tem as normas que exigem a atividade de Chat persistente para serem arquivados e o serviço opcional de conformidade está habilitado, o software de banco de dados do SQL Server é usado para armazenar dados de conformidade, incluindo o conteúdo de bate-papo e eventos, como ingressando e deixando salas. Conteúdo da sala de bate-papo é armazenado no banco de Chat persistente (mgc). Os dados de Conformidade são armazenados no banco de dados de Conformidade (mgccomp). Esses dados são essenciais para os negócios, cujo backup deve ser feito regularmente. 
  
## <a name="back-up-the-databases"></a>Fazer backup dos bancos de dados

Existem duas maneiras de fazer backup de dados de Chat persistente. 
  
- Backup do SQL Server
    
- O cmdlet **Export-CsPersistentChatData** , qual exporta os dados de Chat persistente como um arquivo
    
Dados criados usando o backup do SQL Server requerem espaço em disco significativamente maior – possivelmente 20 vezes maior – que os dados criados pelo **Export-CsPersistentChatData**, mas o backup do SQL Server é o procedimento com o qual os administradores provavelmente já estão familiarizados.
  
Se você quiser usar os procedimentos de backup do SQL Server, consulte a documentação do SQL para obter mais informações. 
  
Se quiser usar o cmdlet **Export-CsPersistentChatData**, você pode especificar o comando da seguinte forma:
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

ou
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Por exemplo, o seguinte comando exporta dados de Chat Persistente do banco de dados de Chat Persistente localizado no servidor atl-sql-001.contoso.com; os dados exportados serão armazenados no arquivo C:\Logs\PersistentChatData.zip. Como o parâmetro Level não foi especificado, comando fará uma exportação completa das informações de Chat Persistente:
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurar os bancos de dados

Como você restaura seus dados de Chat persistente depende do método que você usou para fazer o backup. Se você usou procedimentos de backup do SQL Server, então deve usar procedimentos de restauração do SQL Server. Se você usou o cmdlet **Export-CsPersistentChatData** para fazer backup de dados de Chat persistente, você deve usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

ou
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


