---
title: Skype Implantações locais de várias florestas do Sistema de Sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Skype Room System em um ambiente local de várias florestas.
ms.openlocfilehash: 34b52f32ec3f1c611d8560c8f053e7fbe16b53bf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857038"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Implantações locais de várias florestas do Sistema de Sala
 
Leia este tópico para saber como implantar o Skype Room System em um ambiente local de várias florestas.
  
> [!NOTE]
> Para implantar em várias florestas, o Skype Room System requer Exchange Server 2013 CU6 lançada em 26 de agosto de 2014. Evite o re-uso de uma caixa de correio existente para Skype Room System. Use uma nova caixa de correio de recurso (excluir caixa de correio antiga e re-criar) para Skype Room System. Para restaurar as reuniões perdidas excluindo a caixa de correio, [consulte Conexão ou restaure uma caixa de correio excluída.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Depois de criar a caixa de correio, você pode Set-CalendarProcessing configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes. Depois de criar uma caixa de correio de recurso Exchange para o Skype Room System, habilita a conta do Skype for Business seguindo as etapas em Enableing Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opção 1: Criar uma nova caixa de correio de recurso

Para implantar Skype Room System em um ambiente de várias florestas:
  
1. Crie um Usuário Vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).
    
2. Execute os seguintes comandos no Shell de Gerenciamento Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opção 2: Alterar uma caixa de correio de sala existente para Skype caixa de correio de recurso do Sistema de Sala (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```