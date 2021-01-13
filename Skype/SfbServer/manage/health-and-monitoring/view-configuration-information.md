---
title: Exibir informações de configuração de CDR no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumo: saiba como usar o Registro de Detalhes das Chamadas (CDR) no Skype for Business Server.'
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816631"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de CDR no Skype for Business Server
 
**Resumo:** Saiba como usar o Registro de Detalhes das Chamadas (CDR) no Skype for Business Server.
  
O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala o Skype for Business Server, um único conjunto global de definições de configuração de CDR é criado para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Você pode exibir as definições de configuração de CDR em uso na organização usando o Painel de Controle do Skype for Business Server ou o cmdlet [Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para exibir informações de configuração de CDR usando o Painel de Controle do Skype for Business Server

1. No Painel de Controle do Skype for Business Server, clique **em Monitoramento e Arquivamento.**
    
2. Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de CDR usando cmdlets do Windows PowerShell

Você pode exibir as definições de configuração de CDR usando o Windows PowerShell e o Get-CsCdrConfiguration cmdlet. Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para visualizar informações de configuração do CDR

- Para exibir informações sobre todas as suas definições de configuração de CDR, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
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

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  

