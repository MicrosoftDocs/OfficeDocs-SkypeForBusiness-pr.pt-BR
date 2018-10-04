---
title: Migrar grupos de resposta
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois que os usuários são movidos para Skype para Business Server 2019 pools, você pode migrar seus grupos de resposta. Migrando de resposta grupos inclui copiando os grupos de operadores, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do grupo de resposta da implantação herdada para o Skype para Business Server 2019 pool. Após migrar seus grupos de resposta de legado, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no Skype para Business Server 2019 pool. Chamadas para grupos de resposta não são processadas pelo pool herdado.
ms.openlocfilehash: 89149210e8041fbc84834cec83e1c1fe13d0765c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372934"
---
# <a name="migrate-response-groups"></a>Migrar grupos de resposta

Depois que os usuários são movidos para Skype para Business Server 2019 pools, você pode migrar seus grupos de resposta. Migrando de resposta grupos inclui copiando os grupos de operadores, filas, fluxos de trabalho, arquivos de áudio e mover objetos de contato do grupo de resposta da implantação herdada para o Skype para Business Server 2019 pool. Após migrar seus grupos de resposta de legado, as chamadas para os grupos de resposta são manipuladas pelo aplicativo grupo de resposta no Skype para Business Server 2019 pool. Chamadas para grupos de resposta não são processadas pelo pool herdado.
  
> [!NOTE]
> Embora você possa migrar grupos de resposta antes de mover todos os usuários para o Skype para Business Server 2019 pool, é recomendável que você mova todos os usuários pela primeira vez. Especificamente, os usuários que são os operadores do grupo de resposta não terá funcionalidade completa dos novos recursos até que eles serão movidos para o Skype para Business Server 2019 pool. 
  
Antes de migrar os grupos de resposta, você deve ter implantado um Skype para Business Server 2019 pool que inclui o aplicativo grupo de resposta. Aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice. Você pode garantir que o aplicativo de grupo de resposta está instalado, executando o cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Você pode criar novo Skype para grupos de resposta Business Server 2019 no Skype para Business Server 2019 pool antes de migrar seus grupos de resposta de legado. 
  
Para migrar grupos de resposta de um pool herdado para o Skype para Business Server 2019, você deve executar o cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> O cmdlet de migração do grupo de resposta move a configuração de grupo de resposta para todo o pool. Você não pode selecionar grupos específicos, filas ou fluxos de trabalho para migrar. 
  
Depois de migrar os grupos de resposta, você precisa usar o Skype para painel de controle do Business Server ou Skype para cmdlets do Shell de gerenciamento do servidor de negócios para verificar se todos os grupos de operadores, filas e fluxos de trabalho foram movidos com êxito. 
  
Quando você migra grupos de resposta, os grupos de resposta de legado não serão removidos. Quando você gerencia grupos de resposta após a migração usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios, você pode ver os grupos de resposta de legado e o Skype Business Server 2019 grupos de resposta. Você deve aplicar atualizações somente do Skype Business Server 2019 grupos de resposta. Os grupos de resposta de legado são mantidos apenas para fins de reversão. 
  
> [!CAUTION]
> Após a migração foi concluída e os novos grupos de resposta tem sido criados, o Skype para painel de controle do Business Server e do Skype do Shell de gerenciamento do servidor de negócios exibirá o antigo e Skype para as versões Business Server 2019 cada resposta grupo. Não use Skype para painel de controle do Business Server ou Skype para Business Server Management Shell para remover os grupos de resposta de legado. Se você remover um, o grupo de resposta correspondente que foi criado durante a migração irá parar de funcionar. Os grupos de respostas antigos serão removidos quando você encerrar o pool herdado. 
  
> [!IMPORTANT]
> Recomendamos que você não remova todos os dados da sua implantação anterior até que você encerrar o pool. Além disso, é altamente recomendável que você exporte os grupos de resposta imediatamente após migrar. Se um grupo de resposta de legado deve obter removido, você poderá então restaurar seus grupos de resposta do backup para obter Skype para grupos de resposta Business Server 2019 executar novamente. 
  
Skype para Business Server 2019 introduz um novo recurso de grupo de resposta chamado **Tipo de fluxo de trabalho**. **Tipo de fluxo de trabalho** pode ser **gerenciado** ou **não gerenciado**. Todos os grupos de resposta são migrados com o **Tipo de fluxo de trabalho** definido como **não gerenciado** e uma lista vazia do gerente. 
  
Quando você executa o cmdlet **Move-CsRgsConfiguration** , os grupos de operadores, filas, fluxos de trabalho e arquivos de áudio permanecem no pool herdado para fins de reversão. No entanto, se você precisar reverter para o pool herdado, você precisará executar o cmdlet **Move-CsApplicationEndpoint** para mover objetos de contato de volta para o pool herdado. 
  
O procedimento a seguir para migrar configurações de grupo de resposta pressupõe que você tenha um relacionamento de um para um entre os pools de legado e do Skype para Business Server 2019 pools. Se você pretende consolidar ou dividida até pools durante sua migração e implantação, você precisa planejar qual pool herdado mapeia para o qual Skype para Business Server 2019 pool.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar as configurações de grupo de resposta

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalServerAdmins ou tenha permissões e direitos de administrador equivalentes.
    
2. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
3. Execute:
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por exemplo:
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Após migrar grupos de resposta e operadores para o Skype para Business Server 2019 pool, a URL que os agentes usam para entrar e sair é um Skype para Business Server 2019 URL e está disponível no menu **Ferramentas** . Lembre agentes para atualizar todas as referências, como indicadores, para a nova URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para verificar a migração do grupo de resposta usando Skype para o painel de controle do servidor de negócios

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou minimamente membro da função CsViewOnlyAdministrator.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Open Skype para ferramentas administrativas do Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. No painel de navegação à esquerda, clique em **Grupos de resposta**.
    
4. Na guia **fluxo de trabalho** , verifique se todos os fluxos de trabalho no seu ambiente herdado estão incluídos na lista. 
    
5. Clique na guia **fila** e verifique se todas as filas em seu ambiente herdado estão incluídas na lista. 
    
6. Clique na guia **grupo** e verificar se todos os grupos de agente no seu ambiente herdado estão incluídos na lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para verificar a migração do grupo de resposta usando Skype do Shell de gerenciamento do servidor de negócios

1. Faça logon no computador com uma conta que seja membro do grupo RTCUniversalReadOnlyAdmins ou minimamente membro da função CsViewOnlyAdministrator.
    
2. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
    Para obter detalhes sobre os seguintes cmdlets, execute:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Execute:
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Verifique se todos os grupos de agente no seu ambiente herdado estão incluídos na lista.
    
5. Execute:
    
   ```
   Get-CsRgsQueue
   ```

6. Verifique se todas as filas em seu ambiente herdado estão incluídas na lista.
    
7. Execute:
    
   ```
   Get-CsRgsWorkflow
   ```

8. Verifique se todos os fluxos de trabalho no seu ambiente herdado estão incluídos na lista.
    

