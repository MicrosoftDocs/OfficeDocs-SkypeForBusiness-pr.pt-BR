---
title: Migrar grupos de resposta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019. As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237967"
---
# <a name="migrate-response-groups"></a>Migrar grupos de resposta

Depois que os usuários forem movidos para pools do Skype for Business Server 2019, você poderá migrar seus grupos de resposta. Migrar grupos de resposta inclui copiar grupos de agente, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato de grupo de resposta da implantação herdada para o pool do Skype for Business Server 2019. Depois de migrar seus grupos de resposta herdados, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no pool do Skype for Business Server 2019. As chamadas para grupos de resposta não são mais manipuladas pelo pool herdado.
  
> [!NOTE]
> Embora seja possível migrar grupos de resposta antes de mover todos os usuários para o pool do Skype for Business Server 2019, recomendamos que você mova todos os usuários primeiro. Em particular, os usuários que são agentes de grupo de resposta não terão funcionalidade completa dos novos recursos até serem movidos para o pool do Skype for Business Server 2019. 
  
Antes de migrar grupos de resposta, você deve ter implantado um pool do Skype for Business Server 2019 que inclui o aplicativo de grupo de resposta. O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo do grupo de resposta seja instalado executando o cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Você pode criar novos grupos de resposta do Skype for Business Server 2019 no pool do Skype for Business Server 2019 antes de migrar seus grupos de resposta herdados. 
  
Para migrar grupos de resposta de um pool herdado para o Skype for Business Server 2019, execute o cmdlet **move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> O cmdlet de migração do grupo de resposta move a configuração do grupo de resposta para o pool inteiro. Não é possível selecionar grupos, filas ou fluxos de trabalho específicos para migrar. 
  
Depois de migrar os grupos de resposta, você precisa usar o painel de controle do Skype for Business Server ou cmdlets do Shell de gerenciamento do Skype for Business Server para verificar se todos os grupos de agente, filas e fluxos de trabalho foram movidos com êxito. 
  
Quando você migra grupos de resposta, os grupos de respostas herdadas não são removidos. Ao gerenciar grupos de resposta após a migração usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server, você pode ver os grupos de resposta herdados e os grupos de resposta do Skype for Business Server 2019. Você deve aplicar atualizações somente aos grupos de resposta do Skype for Business Server 2019. Os grupos de respostas herdadas são mantidos somente para fins de recuperação. 
  
> [!CAUTION]
> Após a conclusão da migração e os novos grupos de resposta terem sido criados, o painel de controle do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server exibirão as versões herdadas e do Skype for Business Server 2019 de cada resposta. grupos. Não use o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para remover os grupos de resposta herdados. Se você remover um, o grupo de resposta correspondente criado durante a migração deixará de funcionar. Os grupos de respostas herdadas serão removidos quando você encerrar o pool herdado. 
  
> [!IMPORTANT]
> Recomendamos que você não remova dados de sua implantação anterior até encerrar o pool. Além disso, recomendamos enfaticamente que você exporte os grupos de resposta imediatamente após a migração. Se um grupo de resposta herdado deve ser removido, você pode restaurar seus grupos de resposta do backup para obter os grupos de resposta do Skype for Business Server 2019 em execução novamente. 
  
O Skype for Business Server 2019 apresenta um novo recurso de grupo de resposta chamado **tipo de fluxo de trabalho**. O **tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**. Todos os grupos de resposta são migrados com o **tipo de fluxo de trabalho** definido como **não gerenciado** e com uma lista de gerentes vazia. 
  
Quando você executa o cmdlet **move-CsRgsConfiguration** , os grupos de agente, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão. No entanto, se você precisar reverter para o pool herdado, será necessário executar o cmdlet **move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado. 
  
O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha uma relação um-para-um entre seus pools herdados e os pools do Skype for Business Server 2019. Se você planeja consolidar ou dividir os pools durante a migração e a implantação, será necessário planejar quais pools herdados são mapeados para o pool do Skype for Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Migrar configurações de grupo de resposta

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha direitos e permissões de administrador equivalentes.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
3. Execute:
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por exemplo:
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Depois de migrar grupos de resposta e agentes para o pool do Skype for Business Server 2019, a URL usada pelos agentes para entrar e sair é uma URL do Skype for Business Server 2019 e está disponível no menu **ferramentas** . Lembre os agentes para atualizar todas as referências, como indicadores, para a nova URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para verificar a migração do grupo de resposta usando o painel de controle do Skype for Business Server

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, consulte [abrir ferramentas administrativas do Skype for Business server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. No painel de navegação esquerdo, clique em **grupos de resposta**.
    
4. Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista. 
    
5. Clique na guia **fila** e verifique se todas as filas em seu ambiente herdado estão incluídas na lista. 
    
6. Clique na guia **grupo** e verifique se todos os grupos de agente em seu ambiente herdado estão incluídos na lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para verificar a migração do grupo de resposta usando o Shell de gerenciamento do Skype for Business Server

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou que seja minimamente um membro da função CsViewOnlyAdministrator.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Execute:
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Verifique se todos os grupos de agente do seu ambiente herdado estão incluídos na lista.
    
5. Execute:
    
   ```
   Get-CsRgsQueue
   ```

6. Verifique se todas as filas em seu ambiente herdado estão incluídas na lista.
    
7. Execute:
    
   ```
   Get-CsRgsWorkflow
   ```

8. Verifique se todos os fluxos de trabalho em seu ambiente herdado estão incluídos na lista.
    

