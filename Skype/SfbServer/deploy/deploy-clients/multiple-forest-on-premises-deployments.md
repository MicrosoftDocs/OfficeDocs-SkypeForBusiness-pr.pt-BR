---
title: Implantações locais do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de várias florestas.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093525"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implantações locais do Sistema de Sala do Skype
 
Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de várias florestas.
  
> [!NOTE]
> Para implantar em várias florestas, o Skype Room System requer Exchange Server 2013 CU6 lançada em 26 de agosto de 2014. Evite o re-uso de uma caixa de correio existente para o Sistema de Sala do Skype. Use uma nova caixa de correio de recurso (excluir caixa de correio antiga e re-criar) para o Sistema de Sala do Skype. Para restaurar as reuniões perdidas excluindo a caixa de correio, consulte [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help). 
  
Depois de criar a caixa de correio, você pode Set-CalendarProcessing configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes. Depois de criar uma caixa de correio de Recurso do Exchange para o Skype Room System, habilita a conta do Skype for Business seguindo as etapas em Habilitar contas do sistema de sala do Skype for Skype for Business em implantações locais de floresta única.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opção 1: Criar uma nova caixa de correio de recurso

Para implantar o Sistema de Sala do Skype em um ambiente de várias florestas:
  
1. Crie um Usuário Vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).
    
2. Execute os seguintes comandos no Shell de Gerenciamento Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opção 2: Alterar uma caixa de correio de sala existente para a caixa de correio de recurso do Sistema de Sala do Skype (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```