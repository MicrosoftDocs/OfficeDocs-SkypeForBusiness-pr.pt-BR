---
title: Verificar Replicação de Partição do Esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para verificar se a extensão do esquema foi replicada com êxito na floresta dos serviços de domínio Active Directory, faça o seguinte:'
ms.openlocfilehash: 0b90f61849e66e78c49d7d00783133198bab6b54
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687314"
---
# <a name="verify-replication-of-schema-partition"></a>Verificar Replicação de Partição do Esquema
 
Para verificar se a extensão do esquema foi replicada com êxito na floresta dos serviços de domínio Active Directory, faça o seguinte:
  
1. Faça logon em um controlador de domínio (diferente do controlador de domínio que mantém a função de mestre de esquema) na floresta dos serviços de domínio Active Directory, onde as extensões de esquema foram aplicadas como membro do grupo Administradores da empresa.
    
2. Abrir ADSI Edit: clique em **Iniciar**, em **Ferramentas administrativas**e em **ADSI Editar**.
    
    > [!TIP]
    > Como alternativa, clique em **Iniciar**e em **executar**, digite **ADSIEdit. msc** para iniciar a edição ADSI.
  
3. Na árvore do console de gerenciamento Microsoft (MMC), se ainda não estiver selecionado, clique em ADSI Editar.
    
4. No menu **Ação**, clique em **Conectar-se a**.
    
5. Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
6. No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion. Se esse objeto existir, e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **RangeLower** for 3, o esquema foi atualizado e replicado com sucesso. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **RangeLower** não forem especificados, o esquema não foi modificado ou não foi replicado.
    
> [!NOTE]
> Se a sua verificação da replicação do esquema ainda não mostrar uma replicação bem-sucedida, aguarde cerca de 15 minutos e, em seguida, verifique novamente. A replicação do Active Directory se baseia em um modelo de consistência flexível, e pode ocorrer uma certa latência de replicação, com base em diversos fatores do servidor e da infraestrutura. 
  

