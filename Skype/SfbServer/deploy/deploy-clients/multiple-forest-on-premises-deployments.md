---
title: Implantações locais de várias florestas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.
ms.openlocfilehash: ac9a5edac94d182812aefaf9eb817765c7af6444
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768814"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Implantações locais de várias florestas do Sistema de Salas do Skype
 
Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.
  
> [!NOTE]
> Para implantar em várias florestas, o sistema de sala Skype requer o Exchange Server 2013 CU6 lançado em 26 de agosto de 2014. Evite re-usar uma caixa de correio existente para o sistema de sala do Skype. Use uma caixa de correio de recurso nova (excluir caixa de correio antiga e recriar) para o sistema de sala do Skype. Para restaurar as reuniões perdidas excluindo a caixa de correio, consulte [conectar ou restaurar uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Após a criação da caixa de correio, você pode utilizar Set-CalendarProcessing para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes. Depois de criar uma caixa de correio de recurso do Exchange para o sistema de sala Skype, habilite a conta do Skype for Business seguindo as etapas em como habilitar contas do sistema de sala do Skype para o Skype for Business em implantações locais de floresta únicas.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Opção 1: criar uma nova caixa de correio de recursos

Para implantar o sistema de sala do Skype em um ambiente de várias florestas:
  
1. Criar um Usuário vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).
    
2. Execute os seguintes comandos do Shell de Gerenciamento do Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Opção 2: alterar uma caixa de correio de sala existente para a caixa de correio de recurso do Skype Room System (vinculado)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


