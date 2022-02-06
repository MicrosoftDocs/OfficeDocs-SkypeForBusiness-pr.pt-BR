---
title: Exibir informações de configuração de CDR no Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumo: Saiba como usar o CDR (Registro de Detalhes de Chamada) no Skype for Business Server.'
---

# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de CDR no Skype for Business Server
 
**Resumo:** Saiba como usar o CDR (Registro de Detalhes de Chamada) Skype for Business Server.
  
O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala Skype for Business Server, uma única coleção global de configurações de CDR é criada para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Você pode exibir as configurações de CDR em uso em sua organização usando o Painel de Controle Skype for Business Server ou o cmdlet [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps).
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para exibir informações de configuração de CDR usando Skype for Business Server Painel de Controle

1. Em Skype for Business Server Painel de Controle clique **em Monitoramento e Arquivamento**.
    
2. Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de CDR usando Windows PowerShell cmdlets

Você pode exibir as configurações de CDR usando Windows PowerShell e o cmdlet Get-CsCdrConfiguration cdr. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para visualizar informações de configuração do CDR

- Para exibir informações sobre todas as configurações de CDR, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Isto retorna informações semelhantes à seguinte:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
