---
title: Verificar Replicação de Partição do Esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para verificar se a extensão do esquema foi replicada com êxito em sua floresta dos Serviços de Domínio Active Directory, faça o seguinte:'
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800541"
---
# <a name="verify-replication-of-schema-partition"></a>Verificar a Replicação de Partição do Esquema
 
Para verificar se a extensão do esquema foi replicada com êxito em sua floresta dos Serviços de Domínio Active Directory, faça o seguinte:
  
1. Faça logoff em um controlador de domínio (que não seja o controlador de domínio que detém a função mestra de esquema) em sua floresta dos Serviços de Domínio Active Directory, onde as extensões de esquema foram aplicadas como membro do grupo Administradores de Empresa.
    
2. Abra o Editor ADSI: clique em **Iniciar**, em **Ferramentas Administrativas** e clique em **Editor ADSI**.
    
    > [!TIP]
    > Como alternativa, clique em **Iniciar**, em **Executar**, digite **adsiedit.msc** para iniciar o Editor ADSI.
  
3. Na árvore Console de Gerenciamento Microsoft (MMC) clique em Edição ADSI, se já não está selecionado.
    
4. No menu **Ação**, clique em **Conectar-se a**.
    
5. Na caixa de diálogo **Configurações de Conexão** em **Selecione um Contexto de Nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
6. No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não seguirem a especificação, o esquema não terá sido modificado ou replicado.
    
> [!NOTE]
> Se a sua verificação da replicação ainda não mostrar uma replicação bem-sucedida, aguarde aproximadamente 15 minutos e verifique novamente. A replicação do Active Directory baseia-se em um modelo de consistência solta e pode ocorrer alguma latência de replicação, com base em vários fatores no servidor e na infraestrutura. 
  

