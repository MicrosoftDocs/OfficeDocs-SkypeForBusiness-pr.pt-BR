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
description: Depois que seus usuários são movidos para pools do Skype for Business Server 2019, você pode migrar seus grupos de resposta. A migração de grupos de resposta inclui copiar grupos de agentes, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do Grupo de Resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo Grupo de Resposta no pool do Skype for Business Server 2019. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752673"
---
# <a name="migrate-response-groups"></a>Migrar grupos de resposta

Depois que seus usuários são movidos para pools do Skype for Business Server 2019, você pode migrar seus grupos de resposta. A migração de grupos de resposta inclui copiar grupos de agentes, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do Grupo de Resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são tratadas pelo aplicativo Grupo de Resposta no pool do Skype for Business Server 2019. As chamadas aos grupos de resposta não serão mais processadas pelo pool antigo.
  
> [!NOTE]
> Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Skype for Business Server 2019, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes do grupo de resposta não terão a funcionalidade completa dos novos recursos até que sejam movidos para o pool do Skype for Business Server 2019. 
  
Antes de migrar grupos de resposta, você deve ter implantado um pool do Skype for Business Server 2019 que inclui o aplicativo Grupo de Resposta. O aplicativo Grupo de Resposta é instalado e ativado por padrão quando você implanta o Enterprise Voice. Você pode garantir que o aplicativo grupo de resposta está instalado executando **o cmdlet Get-CsService -ApplicationServer.** 
  
> [!NOTE]
> Você pode criar novos grupos de resposta do Skype for Business Server 2019 no pool do Skype for Business Server 2019 antes de migrar seus grupos de resposta herdados. 
  
Para migrar grupos de resposta de um pool herdado para o Skype for Business Server 2019, execute o cmdlet **Move-CsRgsConfiguration.** 
  
> [!IMPORTANT]
> O cmdlet de migração do Grupo de Resposta move a configuração do Grupo de Resposta para todo o pool. Não é possível selecionar grupos, filas e fluxos de trabalho específicos para migração. 
  
Depois de migrar os grupos de resposta, você precisará usar o Painel de Controle do Skype for Business Server ou os cmdlets do Shell de Gerenciamento do Skype for Business Server para verificar se todos os grupos de agentes, filas e fluxos de trabalho foram movidos com êxito. 
  
Quando você migra grupos de resposta, os grupos de resposta herdados não são removidos. Ao gerenciar grupos de resposta após a migração usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server, você pode ver os grupos de resposta herdados e os grupos de resposta do Skype for Business Server 2019. Você deve aplicar atualizações apenas aos grupos de resposta do Skype for Business Server 2019. Os grupos de resposta herdados são mantidos apenas para fins de reback. 
  
> [!CAUTION]
> Após a conclusão da migração e a criação dos novos grupos de resposta, o Painel de Controle do Skype for Business Server e o Shell de Gerenciamento do Skype for Business Server exibirão as versões herdadas e do Skype for Business Server 2019 de cada grupo de resposta. Não use o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server para remover os grupos de resposta herdados. Se você remover um, o grupo de resposta correspondente criado durante a migração irá parar de funcionar. Os grupos de resposta herdados serão removidos quando você descomissionar o pool herdados. 
  
> [!IMPORTANT]
> Recomendamos que você não remova dados da sua implantação anterior até suspender o pool. Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta herdado for removido, você poderá restaurar seus grupos de resposta do backup para que os grupos de resposta do Skype for Business Server 2019 possam ser executados novamente. 
  
O Skype for Business Server 2019 apresenta um novo recurso do Grupo de Resposta chamado Tipo **de Fluxo de Trabalho.** O **Tipo de fluxo de trabalho** pode ser **Gerenciado** ou **Não gerenciado**. Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido para **Não gerenciado** e com uma lista Gerenciador vazia. 
  
ao executar o cmdlet **Move-CsRgsConfiguration**, os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool de legado para propósitos de reversão. Entretanto, se for necessária uma reversão para o pool antigo, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para transferir objetos de contato de volta para o pool antigo. 
  
O procedimento a seguir para migrar as configurações do Grupo de Resposta presume que você tenha uma relação um-para-um entre seus pools herddos e os pools do Skype for Business Server 2019. Se você planeja consolidar ou dividir pools durante a migração e implantação, será necessário planejar qual pool herdado é mapeado para qual pool do Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar as configurações do Grupo de Resposta

1. Faça logon no computador com uma conta membro do grupo RTCUniversalServerAdmins ou com direitos e permissões do administrador equivalentes.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por exemplo:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Depois de migrar grupos de resposta e agentes para o pool do Skype for Business Server 2019, a URL que os agentes usam para entrar e sair é uma URL do Skype for Business Server 2019 e está disponível no **menu** Ferramentas. Lembre os agentes de atualizar qualquer referência, como indicadores, para o novo URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para verificar a migração do Grupo de Resposta usando o Painel de Controle do Skype for Business Server

1. Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Painel de Controle do Skype for Business Server, consulte Open [Skype for Business Server 2019 administrative tools.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. No painel de navegação à esquerda, clique em **Grupos de Resposta**.
    
4. Na guia **Fluxo de** Trabalho, verifique se todos os fluxos de trabalho em seu ambiente herdável estão incluídos na lista. 
    
5. Clique na **guia Fila** e verifique se todas as filas em seu ambiente herddo estão incluídas na lista. 
    
6. Clique na **guia** Grupo e verifique se todos os grupos de agentes em seu ambiente herdados estão incluídos na lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para verificar a migração do Grupo de Resposta usando o Shell de Gerenciamento do Skype for Business Server

1. Faça logon no computador com uma conta membro do grupo RTCUniversalReadOnlyAdmins ou que seja pelo menos membro da função CsViewOnlyAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Execute:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verifique se todos os grupos de agentes em seu ambiente herdados estão incluídos na lista.
    
5. Execute:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verifique se todas as filas em seu ambiente herdável estão incluídas na lista.
    
7. Execute:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verifique se todos os fluxos de trabalho em seu ambiente herdável estão incluídos na lista.
    

