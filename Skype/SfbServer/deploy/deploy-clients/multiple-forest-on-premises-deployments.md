---
title: Implantações locais de várias florestas do Sistema de Sala do Skype
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
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805741"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implantações locais de várias florestas do Sistema de Sala do Skype
 
Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de várias florestas.
  
> [!NOTE]
> Para implantar em várias florestas, o Sistema de Sala do Skype requer o Exchange Server 2013 CU6 lançado em 26 de agosto de 2014. Evite re-usar uma caixa de correio existente para o Sistema de Sala do Skype. Use uma nova caixa de correio de recurso (excluir a caixa de correio antiga e re-criar) para o Sistema de Sala do Skype. Para restaurar as reuniões perdidas pela exclusão da caixa de correio, consulte [Conectar ou restaurar uma caixa de correio excluída.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Depois de criar a caixa de correio, você pode Set-CalendarProcessing para configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes. Depois de criar uma caixa de correio de Recurso do Exchange para o Sistema de Sala do Skype, habilita a conta do Skype for Business seguindo as etapas em Habilitar contas do Sistema de Sala do Skype para o Skype for Business em implantações locais de floresta única.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opção 1: Criar uma nova caixa de correio de recurso

Para implantar o Sistema de Sala do Skype em um ambiente de várias florestas:
  
1. Criar um Usuário Vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).
    
2. Execute os seguintes comandos no Shell de Gerenciamento do Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opção 2: Alterar uma caixa de correio de sala existente para a caixa de correio de recurso do Sistema de Sala do Skype (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


