---
title: Visualizar informações de configuração do CDR no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumo: Saiba como usar a gravação de detalhes das chamadas (CDR) no Skype para Business Server 2015.'
ms.openlocfilehash: cd143db6ebc0c4e284763ccf4beb9c545fa24ff5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569439"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>Visualizar informações de configuração do CDR no Skype for Business Server 2015
 
**Resumo:** Saiba como usar a gravação de detalhes das chamadas (CDR) no Skype para Business Server 2015.
  
O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala o Skype para Business Server 2015, uma única coleção global de definições de configuração de CDR é criada para você. Os administradores também têm a opção de criar conjuntos de configurações personalizadas que podem ser aplicadas a sites individuais. Você pode exibir as definições de configuração de CDR em uso na sua organização usando Skype para painel de controle do Business Server ou o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para exibir informações de configuração de CDR usando Skype para o painel de controle do servidor de negócios

1. No Skype para painel de controle do Business Server, clique em **monitoramento e arquivamento**.
    
2. Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de CDR usando cmdlets do Windows PowerShell

Você pode exibir as definições de configuração de CDR usando o Windows PowerShell e o cmdlet Get-CsCdrConfiguration. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para visualizar informações de configuração do CDR

- Para exibir informações sobre todas as suas definições de configuração de CDR, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
  ```
  Get-CsCdrConfiguration
  ```

    Isso retornará informações parecidas com:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

