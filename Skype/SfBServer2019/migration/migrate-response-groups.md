---
title: Migrar grupos de resposta
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
description: Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019. Após migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752673"
---
# <a name="migrate-response-groups"></a>Migrar grupos de resposta

Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019. Após migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.
  
> [!NOTE]
> Embora você possa migrar grupos de resposta antes de mover todos os usuários para o pool do Skype for Business Server 2019, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Skype for Business Server 2019. 
  
Antes de migrar grupos de resposta, você deve ter implantado um pool do Skype for Business Server 2019 que inclui o aplicativo grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Você pode criar novos grupos de resposta do Skype for Business Server 2019 no pool do Skype for Business Server 2019 antes de migrar seus grupos de resposta herdados. 
  
Para migrar grupos de resposta de um pool herdado para o Skype for Business Server 2019, execute o cmdlet **move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para todo o pool. Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração. 
  
Após migrar os grupos de resposta, você precisará usar o painel de controle do Skype for Business Server ou os cmdlets do Shell de gerenciamento do Skype for Business Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito. 
  
Quando você migra os grupos de resposta, os grupos de resposta herdados não são removidos. Ao gerenciar grupos de resposta após a migração usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server, você pode ver os grupos de resposta herdados e os grupos de resposta do Skype for Business Server 2019. Você deve aplicar as atualizações somente aos grupos de resposta do Skype for Business Server 2019. Os grupos de respostas herdados são mantidos apenas para fins de recuperação. 
  
> [!CAUTION]
> Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server exibirão as versões herdadas e Skype for Business Server 2019 de cada grupo de resposta. Não use o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para remover os grupos de resposta herdados. Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar. Os grupos de respostas herdados serão removidos quando você encerrar o pool herdado. 
  
> [!IMPORTANT]
> Recomendamos que você não remova dados da sua implantação anterior até suspender o pool. Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta herdado deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Skype for Business Server 2019 em execução novamente. 
  
O Skype for Business Server 2019 introduz um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**. O **Tipo de fluxo de trabalho** pode ser **Gerenciado** ou **Não gerenciado**. Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido para **Não gerenciado** e com uma lista Gerenciador vazia. 
  
ao executar o cmdlet **Move-CsRgsConfiguration**, os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool de legado para propósitos de reversão. Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo. 
  
O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Skype for Business Server 2019. Se você planeja consolidar ou dividir pools durante sua migração e implantação, precisa planejar quais pools herdados mapeiam para qual pool do Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar configurações de grupo de resposta

1. Faça logon no computador com uma conta membro do grupo RTCUniversalServerAdmins ou com direitos e permissões do administrador equivalentes.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.
    
3. Sejam
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por exemplo:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Após migrar grupos de resposta e agentes para o pool do Skype for Business Server 2019, a URL que os agentes usam para entrar e sair é uma URL 2019 do Skype for Business Server e está disponível no menu **ferramentas** . Lembre os agentes de atualizar qualquer referência, como indicadores, para o novo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para verificar a migração do grupo de resposta usando o painel de controle do Skype for Business Server

1. Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, consulte [Open Skype for Business server 2019 Administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. No painel de navegação à esquerda, clique em **Grupos de Resposta**.
    
4. Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista. 
    
5. Clique na guia **fila** e verifique se todas as filas em seu ambiente herdado estão incluídas na lista. 
    
6. Clique na guia **grupo** e verifique se todos os grupos de agente em seu ambiente herdado estão incluídos na lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Skype for Business Server

1. Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Sejam
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verifique se todos os grupos de agente em seu ambiente herdado estão incluídos na lista.
    
5. Sejam
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verifique se todas as filas em seu ambiente herdado estão incluídas na lista.
    
7. Sejam
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista.
    

