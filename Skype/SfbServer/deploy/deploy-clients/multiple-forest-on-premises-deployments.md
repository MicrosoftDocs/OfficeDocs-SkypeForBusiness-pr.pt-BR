---
title: Implantações locais de várias florestas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.
ms.openlocfilehash: 507040a1d8274817e7a4a0780135ee8f6642c77c
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699648"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implantações locais de várias florestas do Sistema de Salas do Skype
 
Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.
  
> [!NOTE]
> Para implantar em várias florestas, o sistema de sala Skype exige Exchange Server 2013 CU6 lançada em 26 de agosto de 2014. Evite reutilizando uma caixa de correio existente para o sistema de sala Skype. Usar um novo (antiga da caixa de correio de excluir e recriar) caixa de correio de recurso para o sistema de sala Skype. Para restaurar as reuniões perdidas com a exclusão da caixa de correio, consulte [Conectar ou restaurar uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Após a criação da caixa de correio, você pode utilizar Set-CalendarProcessing para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes. Depois de criar uma caixa de correio de recurso do Exchange para o sistema de sala do Skype, habilite a conta do Skype para os negócios seguindo as etapas em habilitando contas de sistema do Skype sala para Skype para negócios em implantações em instalações de floresta única.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opção 1: criar uma nova caixa de correio de recursos

Para implantar o sistema de sala do Skype em um ambiente de várias floresta:
  
1. Criar um Usuário vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).
    
2. Execute os seguintes comandos do Shell de Gerenciamento do Exchange Server:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opção 2: Alterar uma caixa de correio de sala existente à caixa de correio de recurso (vinculado) de sistema de sala do Skype

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


