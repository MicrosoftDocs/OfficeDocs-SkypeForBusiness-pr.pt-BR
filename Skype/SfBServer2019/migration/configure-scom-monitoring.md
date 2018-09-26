---
title: Configurar Monitoramento SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a migração para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar Skype para negócios 2019 de servidor funcionar com o System Center Operations Manager.
ms.openlocfilehash: c0d15d14e158c33cda5e623ea978a0bc4f0bb920
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028933"
---
# <a name="configure-scom-monitoring"></a>Configurar Monitoramento SCOM

Após migrar para o Skype para Business Server 2019, você deve concluir algumas tarefas para configurar Skype para negócios 2019 de servidor funcionar com o System Center Operations Manager.
  
- Aplica atualizações a um servidor eleito a gerenciar a lógica de descoberta central.
    
- Atualize a chave de registro do servidor de candidato a descoberta central.
    
- Configure o servidor de gerenciamento do System Center Operations Manager primário para substituir o nó do candidato a descoberta central.
    
Instruções para executar cada uma dessas tarefas são fornecidas abaixo.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplica atualizações a um servidor eleito a gerenciar a lógica de descoberta central.

1. Eleja um servidor que tem o System Center Operations Manager arquivos do agente instalados e esteja configurado como um nó do candidato a descoberta. 
    
2. Aplique atualizações a esse servidor. Consulte o tópico [Aplicar atualizações](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Atualize a chave de registro do servidor de candidato a descoberta central.

1. No servidor eleito a gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell. 
    
2. Na linha de comando, digite o seguinte:
    
  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
  ```

  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
  ```

    > [!NOTE]
    > Sempre que você edite o registro, você pode enfrentar um erro dizendo que o comando falha se a chave do registro já existir. Se você enfrentar isso, você pode ignorar com segurança o erro. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure seu servidor de gerenciamento do System Center Operations Manager primário para substituir o nó de Inspetor do candidato a descoberta central.

1. Em um computador onde o console do System Center Operations Manager foi instalado, expanda **Objetos do pacote de gerenciamento** e selecione **Descobertas de objeto**.
    
2. Clique em **Alterar escopo**
    
3. Na página de **Objetos do pacote de gerenciamento de escopo** , selecione **Candidato a descoberta LS**.
    
4. Substitua o **Valor efetivo de candidato de descoberta LS** para o nome do servidor candidato eleito no procedimento anterior. 
    
Finalize as alterações, reinicie o serviço de integridade no servidor de gerenciamento do System Center Operations Manager raiz.
  

