---
title: Habilitar gravação de detalhes da chamada no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: Saiba como habilitar detalhes das chamadas (CDR) registros de gravação no Skype para Business Server 2015.'
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a>Habilitar gravação de detalhes da chamada no Skype for Business Server 2015
 
**Resumo:** Aprenda a habilitar detalhes das chamadas (CDR) registros de gravação no Skype para Business Server 2015.
  
O CDR (registro de detalhes das chamadas) registra informações de utilização e diagnóstico sobre atividades ponto a ponto, incluindo serviço de mensagens instantâneas, chamadas do protocolo VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões. Os dados de uso podem ser utilizados para calcular o ROI (retorno sobre o investimento), enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões. 
  
Use o procedimento a seguir para ativar o CDR para a organização inteira ou para cada local da organização.
  
> [!NOTE]
> Para habilitar o CDR, é preciso configurar o monitoramento e o banco de dados de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar o CDR com Skype para painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes das Chamadas**. 
    
4. Na página **Registro de Detalhes das Chamadas**, clique no local apropriado na tabela, em **Ação** e em **Habilitar CDR**.
    
    > [!NOTE]
    > O CDR é ativado por padrão. 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitando o CDR usando cmdlets do Windows PowerShell

É possível habilitar o CDR usando o Windows PowerShell e o cmdlet **Set-CsCdrConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar o CDR para um único local

 Para desabilitar o CDR, defina o parâmetro EnableCDR como Verdadeiro ($True).
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para desabilitar o CDR para um único local

 Para desabilitar o CDR, defina o parâmetro EnableCDR como Falso ($False). Desabilitar o CDR não desinstalará o monitoramento, apenas pausará a coleta e o armazenamento de dados de CDR.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Para usar um único comando para habilitar o CDR em vários locais

 Este comando habilita o CDR para todas as configurações do CDR em uso na sua organização.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Consulte também

[Planejamento do monitoramento](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Implantando o Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)