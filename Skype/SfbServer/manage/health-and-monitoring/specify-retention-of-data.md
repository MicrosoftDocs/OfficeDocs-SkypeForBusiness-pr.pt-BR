---
title: Especifique a retenção de dados cdr no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Resumo: saiba como gerenciar dados de cdr (registro de detalhes de chamada) para Skype for Business Server.'
ms.openlocfilehash: b232e853e28f2dbdee33c666e65ca89932796941
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852005"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Especifique a retenção de dados cdr no Skype for Business Server
 
**Resumo:** Saiba como gerenciar dados de registro de detalhes de chamada (CDR) para Skype for Business Server.
  
Por padrão, os dados de CDR (registro de detalhes das chamadas) são purgados após 60 dias. É possível usar as configurações da página **Registro de Detalhes das Chamadas** para manter os dados por um período maior ou menor. Se você desabilitar o CDR, os dados que foram capturados antes da desabilitação do CDR também poderão ser purgados.
  
> [!NOTE]
> Você deve configurar o CDR e a QoE (Qualidade da Experiência) para reter os dados durante o mesmo número de dias. Cada chamada nos CDRs (relatórios de detalhes de chamada), disponível na página da web de Relatórios do Monitoring Serve, inclui informações de CDR e QoE. Se a duração da limpeza de CDR e QoE for diferente, algumas chamadas poderão incluir apenas dados de CDR, enquanto outras poderão incluir apenas dados de QoE. 
  
Use o procedimento a seguir para definir as configurações de limpeza de dados de CDR. 
  
### <a name="to-specify-retention-of-cdr-data"></a>Para especificar a retenção de dados de CDR

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.
    
4. Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.
    
5. Para ativar a limpeza, selecione **Habilitar limpeza CDRs**.
    
6. Em **Manter CDRs por um período máximo (dias):** selecione o número máximo de dias que os registros de detalhes de chamada devem ser retidos.
    
7. Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.
    
8. Clique em **Confirmar**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificando a retenção de CDR usando Windows PowerShell cmdlets

É possível criar configurações de retenção CDR usando o Windows PowerShell e o cmdlet Set-CsCdrConfiguration. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>Para especificar a retenção de CDR para um local específico

- Este comando habilita a exclusão de dados CDR para o local Redmond e configura o local para manter os dados CDR e os dados do relatório de erro por 20 dias.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>Para especificar a retenção CDR para vários locais

- Este comando configura a retenção CDR para todas as definições de configuração CDR em uso em uma organização.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Confira também

[CdR (registro de detalhes de chamada) no Skype for Business Server](call-detail-recording-cdr.md)