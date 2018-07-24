---
title: Especificar a retenção de dados de CDR em Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumo: Saiba como gerenciar os detalhes da chamada (CDR) dados de gravação para Skype para Business Server.'
ms.openlocfilehash: ce35d8d2cac0968cca912031ec5e406ebe93e2eb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005829"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Especificar a retenção de dados de CDR em Skype para Business Server
 
**Resumo:** Saiba como gerenciar os detalhes da chamada (CDR) dados de gravação para Skype para Business Server.
  
Por padrão, os dados de CDR (registro de detalhes das chamadas) são purgados após 60 dias. É possível usar as configurações da página **Registro de Detalhes das Chamadas** para manter os dados por um período maior ou menor. Se você desabilitar o CDR, os dados que foram capturados antes da desabilitação do CDR também poderão ser purgados.
  
> [!NOTE]
> Você deve configurar o CDR e a QoE (Qualidade da Experiência) para reter os dados durante o mesmo número de dias. Cada chamada nos CDRs (relatórios de detalhes de chamada), disponível na página da web de Relatórios do Monitoring Serve, inclui informações de CDR e QoE. Se a duração da limpeza de CDR e QoE for diferente, algumas chamadas poderão incluir apenas dados de CDR, enquanto outras poderão incluir apenas dados de QoE. 
  
Use o procedimento a seguir para definir as configurações de limpeza de dados de CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Para especificar a retenção de dados de CDR

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.
    
4. Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.
    
5. Para ativar a limpeza, selecione **Habilitar limpeza CDRs**.
    
6. Em **Manter CDRs por um período máximo (dias):** selecione o número máximo de dias que os registros de detalhes de chamada devem ser retidos.
    
7. Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.
    
8. Clique em **Confirmar**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificar a retenção de CDR usando cmdlets do Windows PowerShell

Você pode criar configurações de retenção de CDR usando o Windows PowerShell e o cmdlet Set-CsCdrConfiguration. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Para especificar a retenção de CDR para um local específico

- Este comando habilita a exclusão de dados CDR para o local Redmond e configura o local para manter os dados CDR e os dados do relatório de erro por 20 dias.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Para especificar a retenção CDR para vários locais

- Este comando configura a retenção CDR para todas as definições de configuração CDR em uso em uma organização.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Consulte também

[Gravação (CDR) no Skype para Business Server de detalhes da chamada](call-detail-recording-cdr.md)