---
title: Exibir informações de configuração de CDR no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Resumo: saiba como usar a CDR (gravação de detalhes de chamadas) no Skype for Business Server.'
ms.openlocfilehash: e0aed0c26672b83cb223ba763eb6224025d68118
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279645"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Exibir informações de configuração de CDR no Skype for Business Server
 
**Resumo:** Saiba como usar a CDR (gravação de detalhes de chamadas) no Skype for Business Server.
  
O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala o Skype for Business Server, uma única coleção global de definições de configuração de CDR é criada para você. Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais. Você pode exibir as configurações de CDR em uso em sua organização usando o painel de controle do Skype for Business Server ou o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Para exibir as informações de configuração de CDR usando o painel de controle do Skype for Business Server

1. No painel de controle do Skype for Business Server, clique em **monitoramento e arquivamento**.
    
2. Uma lista com todas as configurações de CDR será exibida na guia **Registro de Detalhes de Chamada**. Para cada conjunto de configurações, você verá o **Nome** do conjunto; se o CDR foi habilitado ou não (a propriedade **CDR**); e se a limpeza foi habilitada ou não (a propriedade **Limpeza de CDR**). Para ver informações detalhadas sobre um conjunto, clique duas vezes no conjunto ou selecione o conjunto correto, clique em **Editar** e em **Mostrar Detalhes**. Observe que só é possível visualizar informações detalhadas de um conjunto de configurações de CDR por vez.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de CDR usando cmdlets do Windows PowerShell

Você pode exibir as configurações de configuração de CDR usando o Windows PowerShell e o cmdlet Get-CsCdrConfiguration. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Para visualizar informações de configuração do CDR

- Para ver as informações sobre todas as suas configurações de CDR, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
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

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

