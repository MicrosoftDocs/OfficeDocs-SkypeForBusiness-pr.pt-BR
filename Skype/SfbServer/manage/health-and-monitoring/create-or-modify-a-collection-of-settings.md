---
title: Criar ou modificar uma coleção de definições de configuração de CDR em Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumo: Saiba mais sobre os detalhes de chamada (CDR) de gravação no Skype para Business Server.'
ms.openlocfilehash: 563aeb37a0d6ae8cc10f73fe8d5d6808b9a051a9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199747"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Criar ou modificar uma coleção de definições de configuração de CDR em Skype para Business Server
 
**Resumo:** Saiba mais sobre os detalhes da chamada (CDR) de gravação no Skype para Business Server.
  
O registro de detalhes das chamadas (CDR) permite rastrear o uso de coisas como sessões de mensagens instantâneas ponto a ponto, telefonemas de protocolo VoIP (voz sobre Internet) e chamadas em conferência. Esses dados de uso incluem informações sobre quem ligou para quem, quando a ligação foi feita e quanto tempo durou a conversa.
  
Quando você instala o Skype para Business Server uma única coleção global de definições de configuração de CDR é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que essas configurações de escopo local forem usadas, elas terão precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo local para o local Redmond, essas configurações (e não as configurações globais) serão usadas para gerenciar CDR em Redmond.
  
Você pode criar definições de configuração de CDR usando qualquer um dos Skype para painel de controle do Business Server ou o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Você pode usar o Skype para painel de controle do Business Server ou o cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar definições existentes. Se você estiver usando o Skype para painel de controle do Business Server para criar ou modificar as configurações, as seguintes opções estarão disponíveis para você:
  
|**Configuração de interface do usuário**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo das definições de configuração CDR sendo criada. Estas configurações podem ser criadas apenas no escopo local.  <br/> |
|Habilitar monitoramento de CDRs  <br/> |EnableCDR  <br/> |Indica se o CDR está habilitado ou não.  <br/> |
|Habilitar exclusão de CDRs  <br/> |EnablePurging  <br/> |Indica se os registros do CDR serão excluídos periodicamente ou não do banco de dados do CDR.  <br/> |
|Manter CDRs pela duração máxima (dias)  <br/> |KeepCallDetailForDays  <br/> |Indica o número de dias que os registros CDR serão mantidos no banco de dados de CDR. Qualquer registro anterior ao número de dias especificado será automaticamente excluído. (Observe que excluir ocorrerá apenas se a exclusão tiver habilitada.)  <br/> |
|Manter os dados do relatório de erro pela duração máxima (dias)  <br/> |KeepErrorReportForDays  <br/> |Indica o número de dias que os relatórios de erros do CDR são mantidos. Qualquer relatório mais antigo do que o número de dias especificado será automaticamente excluído. Os relatórios de erros do CDR são relatórios de diagnósticos carregados por aplicativos cliente.  <br/> |
   
> [!NOTE]
> Os cmdlets New-CsCdrConfiguration e Set-CsCdrConfiguration incluem opções adicionais não estão disponíveis no Skype para painel de controle do servidor de negócios. Consulte o [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) e os tópicos de Ajuda [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para obter mais informações.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar definições de configuração de CDR usando Skype para o painel de controle do servidor de negócios

1. No Skype para painel de controle do Business Server, clique em **monitoramento e arquivamento**.
    
2. Na guia **Registro de detalhes de chamada** , clique em **novo**.
    
3. Na caixa de diálogo **Selecionar um local**, selecione o local onde as novas definições de configuração devem ser criadas. Se a caixa de diálogo estiver vazia, isso significa que a todos os seus locais já foi atribuído um conjunto de definições de configuração do CDR. Cada local é limitado a um único conjunto. Nesse caso, é possível excluir e recriar as configurações ou apenas modificar as configurações existentes.
    
4. Na caixa de diálogo **Nova configuração do Registro de detalhes das chamadas (CDR)**, faça as seleções desejadas e clique em **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar as definições de configuração CDR existentes usando Skype para o painel de controle do servidor de negócios

1. No Skype para painel de controle do Business Server, clique em **monitoramento e arquivamento**.
    
2. Clique duas vezes no conjunto de configurações a ser modificado ou selecione o conjunto e, em seguida, clique em **Editar** e em **Exibir detalhes**. Observe que você pode apenas modificar um único conjunto por vez. Para fazer as mesmas alterações vários conjuntos, use o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Na caixa de diálogo **Editar configurações de Registro de detalhes das chamadas (CDR)**, faça as seleções desejadas e clique em **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando definições de configuração de CDR usando Cmdlets do Windows PowerShell

Você pode criar a configuração de CDR configurações também podem ser criadas usando o Windows PowerShell e o cmdlet **New-CsCdrConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de CDR

 Este comando cria um novo conjunto de definições de configuração de CDR aplicadas ao local Redmond:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para criar um conjunto de definições de configuração de CDR que desabilitam o registro de detalhes das chamadas

 Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando precedente, o novo conjunto de definições de configurações usará os valores padrão para todas as suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de definições de configuração de Detalhes das Chamadas que, por padrão, permite desabilitar o registro de Detalhes das Chamadas, use um comando como este:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração de CDR

 É possível modificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter registros de Detalhes das Chamadas por 30 dias e relatórios de erro por 90 dias:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

