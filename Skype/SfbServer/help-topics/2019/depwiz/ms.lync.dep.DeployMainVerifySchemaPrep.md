---
title: Verificar a replicação de partição do esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para verificar se a extensão do esquema foi replicada com êxito em sua floresta do Active Directory Domain Services, faça o seguinte:'
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="verify-replication-of-schema-partition"></a>Verificar a replicação de partição do esquema
 
Para verificar se a extensão do esquema foi replicada com êxito em sua floresta do Active Directory Domain Services, faça o seguinte:
  
1. Faça logon um controlador de domínio (que não seja um controlador de domínio que detém a função de mestre de esquema) em sua floresta do Active Directory Domain Services, onde as extensões de esquema foram aplicadas como membro do grupo Administradores de empresa.
    
2. Abrir o ADSI Edit: Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em Editor **ADSI**.
    
    > [!TIP]
    > Como alternativa, clique em **Iniciar**, clique em **Executar**, tipo **ADSIEdit. msc** para iniciar o ADSI Edit.
  
3. Na árvore do Console de gerenciamento Microsoft (MMC), se não ainda estiver selecionada, clique em Editor ADSI.
    
4. No menu **Ação**, clique em **Conectar-se a**.
    
5. Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
6. No contêiner de esquema, procure por CN = ms-RTC-SIP-SchemaVersion. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** é 3, em seguida, o esquema foi com êxito atualizado e replicado. Se este objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não são como especificado, em seguida, o esquema não foi modificado ou não foi replicado.
    
> [!NOTE]
> Se a sua seleção da replicação do esquema não mostrar uma replicação bem-sucedida ainda, aguarde aproximadamente 15 minutos e verifique novamente. Replicação do Active Directory é baseada em um modelo de consistência ampliada e alguns latência de replicação pode ocorrer, com base em vários fatores no servidor e infra-estrutura. 
  

