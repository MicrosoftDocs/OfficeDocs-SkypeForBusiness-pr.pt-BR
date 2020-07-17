---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após a migração para o Microsoft Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754041"
---
# <a name="configure-scom-monitoring"></a>Configurar monitoramento SCOM

Após a migração para o Skype for Business Server 2019, você deve concluir algumas tarefas para configurar o Skype for Business Server 2019 para trabalhar com o System Center Operations Manager.
  
- Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.
    
- Atualize a chave de registro do servidor candidato a descoberta central.
    
- Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó de descoberta central de candidatos.
    
Instruções para executar cada uma dessas tarefas são fornecidas abaixo.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Aplicar atualizações a um servidor escolhido para gerenciar a lógica de descoberta central.

1. Eleja um servidor que possua os arquivos do agente do Gerenciador de Operações do Sistema Central instalados e esteja configurado como nó de descoberta central. 
    
2. Aplicar atualizações a este servidor. Consulte o tópico [Apply updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Atualize a chave de registro do servidor candidato a descoberta central.

1. No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell. 
    
2. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Sempre que você editar o registro, você poderá receber um erro em que o comando falha caso a chave de registro já exista. Caso isso aconteça, você pode ignorar com segurança o erro. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó do Inspetor de descoberta central de candidatos.

1. Em um computador onde o console do Gerenciador de Operações do  System Center foi instalado, expanda **Objetos do Pacote de Gerenciamento** e selecione **Descobertas de Objeto**.
    
2. Clique em **alterar escopo**
    
3. Da página **Escopo de Objetos do Pacote de Gerenciamento**, selecione **Candidato a Descoberta LS**.
    
4. Substitua o **Valor Efetivo de Candidato a Descoberta LS** para o nome do servidor de candidato eleito para o procedimento anterior. 
    
Para finalizar suas alterações, reinicie o serviço de integridade no servidor de gerenciamento raiz do System Center Operations Manager.
  

