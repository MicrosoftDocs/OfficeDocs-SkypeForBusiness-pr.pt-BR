---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois de migrar para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813799"
---
# <a name="configure-scom-monitoring"></a>Configurar monitoramento SCOM

Depois de migrar para o Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
  
- Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.
    
- Atualize a chave do registro do servidor candidato à descoberta central.
    
- Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó de descoberta central de candidatos.
    
As instruções para executar cada uma dessas tarefas são fornecidas abaixo.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.

1. Escolha um servidor que tenha os arquivos de agente do System Center Operations Manager instalados e esteja configurado como um nó de descoberta de candidatos. 
    
2. Aplicar atualizações a este servidor. Consulte o tópico [aplicar atualizações](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Atualize a chave do registro do servidor candidato à descoberta central.

1. No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell. 
    
2. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Sempre que você edita o registro, pode ocorrer um erro inque o comando falhou se a chave do registro já existe. Se isso acontecer, você pode ignorar o erro com segurança. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó do inspetor da descoberta do candidato.

1. Em um computador em que o console System Center Operations Manager foi instalado, expanda os **objetos do pacote de gerenciamento** e selecione descobertas de **objetos**.
    
2. Clique em **alterar escopo**
    
3. Na página **objetos do pacote de gerenciamento de escopo** , selecione **candidato para descoberta ls**.
    
4. Substitua o **valor efetivo de candidato à descoberta ls** pelo nome do servidor de candidatos escolhido no procedimento anterior. 
    
Para finalizar suas alterações, reinicie o serviço de integridade no servidor de gerenciamento raiz do System Center Operations Manager.
  

