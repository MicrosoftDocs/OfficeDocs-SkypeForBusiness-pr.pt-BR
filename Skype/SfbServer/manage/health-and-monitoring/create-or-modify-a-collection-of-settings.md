---
title: Criar ou modificar uma coleção de configurações de CDR no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Resumo: Saiba mais sobre o CDR (registro de detalhes de chamada) no Skype for Business Server.'
---

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Criar ou modificar uma coleção de configurações de CDR no Skype for Business Server
 
**Resumo:** Saiba mais sobre a gravação de detalhes de chamada (CDR) no Skype for Business Server.
  
O registro de detalhes da chamada (CDR) permite rastrear o uso de coisas como sessões de mensagem instantânea ponto a ponto, chamadas de telefone Protocolo Voz por Internet (VoIP) e chamadas de conferência. Este dados de uso inclui informações sobre quem ligou para quem, quando realizou a ligação e quanto tempo foi a conversa.
  
Quando você instala Skype for Business Server uma única coleção global de configurações de CDR é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo local para o local Redmond, estas configurações (ao invés das configurações globais) serão usadas para gerenciar CDR em Redmond.
  
Você pode criar configurações de CDR usando o Painel de Controle Skype for Business Server ou o cmdlet [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps). Você pode usar Skype for Business Server Painel de Controle ou o cmdlet [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para modificar as configurações existentes. Se você estiver usando Skype for Business Server Painel de Controle para criar ou modificar configurações, as seguintes opções estarão disponíveis para você:
  
|**Configuração da interface do usuário**|**Parâmetro PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo das definições de configuração CDR sendo criada. Estas configurações podem ser criadas apenas no escopo local.  <br/> |
|Habilitar monitoramento de CDRs  <br/> |EnableCDR  <br/> |Indica se o CDR está ou não habilitado.  <br/> |
|Habilitar exclusão de CDRs  <br/> |EnablePurging  <br/> |Indica se os registros CDR serão ou não periodicamente excluídos do banco de dados de CDR.  <br/> |
|Manter CDRs pela duração máxima (dias)  <br/> |KeepCallDetailForDays  <br/> |Indica o número de dias que os registros CDR serão mantidos no banco de dados de CDR. Qualquer registro anterior ao número de dias especificado será automaticamente excluído. (Observe que excluir ocorrerá apenas se a exclusão tiver habilitada.)  <br/> |
|Manter os dados do relatório de erro pela duração máxima (dias)  <br/> |KeepErrorReportForDays  <br/> |Indica o número de dias que os relatórios de erros do CDR são mantidos. Qualquer relatório mais antigo do que o número de dias especificado será automaticamente excluído. Os relatórios de CDR são relatórios de diagnósticos, carregados por aplicativos cliente.  <br/> |
   
> [!NOTE]
> Os cmdlets New-CsCdrConfiguration e Set-CsCdrConfiguration incluem opções adicionais não disponíveis Skype for Business Server Painel de Controle. Consulte os [tópicos de ajuda New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) e [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) para obter mais informações.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar configurações de CDR usando Skype for Business Server Painel de Controle

1. Em Skype for Business Server Painel de Controle clique **em Monitoramento e Arquivamento**.
    
2. Na guia **Registro de Detalhes da Chamada** , clique em **Novo**.
    
3. Na caixa de diálogo **Selecionar um local**, selecione o local onde as novas definições de configuração devem ser criadas. Se a caixa de diálogo estiver vazia, isto significa que todos os seus locais já foram atribuídos com um conjunto de definições de configuração CDR. Cada local é limitado para um único conjunto. Neste caso, é possível excluir e recriar as configurações ou apenas modificar as configurações existentes.
    
4. Na caixa de diálogo **Nova configuração CDR**, faça as seleções desejadas e clique em **Confirmar**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar as configurações de CDR existentes usando Skype for Business Server Painel de Controle

1. Em Skype for Business Server Painel de Controle clique **em Monitoramento e Arquivamento**.
    
2. Clique duas vezes no conjunto de configurações a ser modificado ou selecione o conjunto, clique em **Editar** e em **Exibir detalhes**. Observe que você pode apenas modificar um único conjunto por vez. Para fazer as mesmas alterações em várias coleções, use o Shell Skype for Business Server Gerenciamento.
    
3. Na caixa de diálogo **Editar configuração de CDR**, certifique-se de fazer as seleções desejadas e clique em **Confirmar**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando configurações de CDR usando Windows PowerShell Cmdlets

Você também pode criar configurações de CDR usando o Windows PowerShell e o cmdlet **New-CsCdrConfiguration**. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para criar um novo conjunto de definições de configuração CDR

 Este comando cria um novo conjunto de definições de configuração CDR aplicadas ao local Redmond:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para criar um conjunto de definições de configuração CDR que desabilitam o registro de detalhes da chamada

 Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de Detalhe da Chamada que, por padrão, permite desabilitar o registro de Detalhes da chamada, use um comando como este:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração CDR

 É possível modificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter registros de Detalhe da Chamada por 30 dias e relatórios de erro por 90 dias:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) .
