---
title: Excluir uma coleção existente de definições de configuração de CDR no Skype for Business Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumo: saiba como remover as configurações de CDR no Skype for Business Server.'
---

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Excluir uma coleção existente de definições de configuração de CDR no Skype for Business Server
 
**Resumo:** Saiba como remover as configurações de CDR no Skype for Business Server.
  
O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala Skype for Business Server, uma única coleção global de configurações de CDR é criada para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global. Se você excluir as configurações com escopo de site, o CDR será gerenciado nesse site usando as configurações globais.
  
Observe que você também pode "excluir" as configurações globais. Contudo, elas não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a purga está habilitada em uma coleção de configurações de CDR. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão. Nesse caso, isso significa que a exclusão será habilitada novamente.
  
Você pode remover as configurações de CDR usando o Painel de Controle Skype for Business Server ou o cmdlet [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps).
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Para remover as configurações de CDR com Skype for Business Server Painel de Controle

1. Em Skype for Business Server Painel de Controle, clique **em Monitoramento e Arquivamento**. 
    
2. Na guia **Registro de Detalhes de** Chamada, selecione a coleção (ou coleções) das configurações de CDR a serem removidas. Para selecionar várias coleções, clique na primeira coleção, segure a tecla Ctrl e clique em coleções adicionais.
    
3. Clique **em Editar** e em **Excluir**.
    
4. Na caixa Skype for Business Server Painel de Controle, clique em **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo configurações de CDR usando Windows PowerShell Cmdlets

Você pode excluir definições de configuração de registro de detalhes de chamada usando Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration**. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para remover uma coleção especificada de configurações de CDR

 Este comando remove as configurações de CDR aplicadas ao site redmond:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as configurações de CDR aplicadas ao escopo do site

 Este comando remove todas as configurações de CDR aplicadas ao escopo do site:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Confira também

[Limpar manualmente o registro de detalhes de chamada e os bancos de dados de Qualidade da Experiência no Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)