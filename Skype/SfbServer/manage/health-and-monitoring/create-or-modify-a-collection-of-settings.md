---
title: Criar ou modificar um conjunto de configurações de configuração de CDR no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumo: Saiba mais sobre a gravação de detalhes de chamadas (CDR) no Skype for Business Server.'
ms.openlocfilehash: 52c5f3de5b3c83fe5701b339ecf45ed7f80a0988
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992518"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Criar ou modificar um conjunto de configurações de configuração de CDR no Skype for Business Server
 
**Resumo:** Saiba mais sobre a gravação de detalhes de chamadas (CDR) no Skype for Business Server.
  
O registro de detalhes das chamadas (CDR) permite rastrear o uso de coisas como sessões de mensagens instantâneas ponto a ponto, telefonemas de protocolo VoIP (voz sobre Internet) e chamadas em conferência. Esses dados de uso incluem informações sobre quem ligou para quem, quando a ligação foi feita e quanto tempo durou a conversa.
  
Ao instalar o Skype for Business Server, uma única coleção global de definições de configuração de CDR é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que essas configurações de escopo local forem usadas, elas terão precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo local para o local Redmond, essas configurações (e não as configurações globais) serão usadas para gerenciar CDR em Redmond.
  
Você pode criar definições de configuração de CDR usando o painel de controle do Skype for Business Server ou o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) . Você pode usar o painel de controle do Skype for Business Server ou o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar as configurações existentes. Se você estiver usando o painel de controle do Skype for Business Server para criar ou modificar as configurações, as seguintes opções estarão disponíveis para você:
  
|**Configuração de interface do usuário**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo das definições de configuração CDR sendo criada. Estas configurações podem ser criadas apenas no escopo local.  <br/> |
|Habilitar monitoramento de CDRs  <br/> |EnableCDR  <br/> |Indica se o CDR está habilitado ou não.  <br/> |
|Habilitar exclusão de CDRs  <br/> |EnablePurging  <br/> |Indica se os registros do CDR serão excluídos periodicamente ou não do banco de dados do CDR.  <br/> |
|Manter CDRs pela duração máxima (dias)  <br/> |KeepCallDetailForDays  <br/> |Indica o número de dias que os registros CDR serão mantidos no banco de dados de CDR. Qualquer registro anterior ao número de dias especificado será automaticamente excluído. (Observe que excluir ocorrerá apenas se a exclusão tiver habilitada.)  <br/> |
|Manter os dados do relatório de erro pela duração máxima (dias)  <br/> |KeepErrorReportForDays  <br/> |Indica o número de dias que os relatórios de erros do CDR são mantidos. Qualquer relatório mais antigo do que o número de dias especificado será automaticamente excluído. Os relatórios de erros do CDR são relatórios de diagnósticos carregados por aplicativos cliente.  <br/> |
   
> [!NOTE]
> Os cmdlets New-CsCdrConfiguration e Set-CsCdrConfiguration incluem opções adicionais que não estão disponíveis no painel de controle do Skype for Business Server. Consulte os tópicos de ajuda [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) e [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para obter mais informações.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar definições de configuração de CDR usando o painel de controle do Skype for Business Server

1. No painel de controle do Skype for Business Server, clique em **monitoramento e arquivamento**.
    
2. Na guia **gravação de detalhes da chamada** , clique em **novo**.
    
3. Na caixa de diálogo **Selecionar um local**, selecione o local onde as novas definições de configuração devem ser criadas. Se a caixa de diálogo estiver vazia, isso significa que a todos os seus locais já foi atribuído um conjunto de definições de configuração do CDR. Cada local é limitado a um único conjunto. Nesse caso, é possível excluir e recriar as configurações ou apenas modificar as configurações existentes.
    
4. Na caixa de diálogo **Nova configuração do Registro de detalhes das chamadas (CDR)**, faça as seleções desejadas e clique em **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar as definições de configuração de CDR existentes usando o painel de controle do Skype for Business Server

1. No painel de controle do Skype for Business Server, clique em **monitoramento e arquivamento**.
    
2. Clique duas vezes no conjunto de configurações a ser modificado ou selecione o conjunto e, em seguida, clique em **Editar** e em **Exibir detalhes**. Observe que você pode apenas modificar um único conjunto por vez. Para fazer as mesmas alterações em várias coleções, use o Shell de gerenciamento do Skype for Business Server em vez disso.
    
3. Na caixa de diálogo **Editar configurações de Registro de detalhes das chamadas (CDR)**, faça as seleções desejadas e clique em **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como criar definições de configuração de CDR usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de CDR também podem ser criadas usando o Windows PowerShell e o cmdlet **New-CsCdrConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de CDR

 Este comando cria um novo conjunto de definições de configuração de CDR aplicadas ao local Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para criar um conjunto de definições de configuração de CDR que desabilitam o registro de detalhes das chamadas

 Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando precedente, o novo conjunto de definições de configurações usará os valores padrão para todas as suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de definições de configuração de Detalhes das Chamadas que, por padrão, permite desabilitar o registro de Detalhes das Chamadas, use um comando como este:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração de CDR

 É possível modificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter registros de Detalhes das Chamadas por 30 dias e relatórios de erro por 90 dias:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
  

