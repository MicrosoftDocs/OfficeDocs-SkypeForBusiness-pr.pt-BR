---
title: Configurar o registro de detalhes de chamada e as configurações de Qualidade da Experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumo: saiba como configurar CDR e QoE em Skype for Business Server.'
ms.openlocfilehash: 9275ead7fee4b9751141dd683bafb8b41e077530
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839633"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurar o registro de detalhes de chamada e as configurações de Qualidade da Experiência no Skype for Business Server
 
**Resumo:** Saiba como configurar CDR e QoE em Skype for Business Server.
  
Configure o monitoramento de CDR e QoE usando SQL Server Reporting Services relatórios para Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurar CDR e QoE

Depois de associar um armazenamento de monitoramento a um pool de Front-End, configure o armazenamento de monitoramento e instale e configure o SQL Server Reporting Services e Relatórios de Monitoramento, você pode gerenciar o cdr (registro de detalhes de chamada) e o monitoramento de Qualidade da Experiência (QoE) usando o Shell de Gerenciamento Skype for Business Server. Skype for Business Server Os cmdlets do Shell de Gerenciamento permitem que você habilita e desabilite o monitoramento de CDR e/ou QoE para um site específico ou para toda a implantação Skype for Business Server. que pode ser feito com um comando tão simples quanto este:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Ao instalar o Skype for Business Server, você também instalará uma coleção predefinida de configurações globais para CDR e QoE. Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se o CDR está habilitado ou não. Se for Verdadeiro, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.  <br/> |Verdadeiro  <br/> |
|EnablePurging  <br/> |Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.  <br/> |Verdadeiro  <br/> |
|KeepCallDetailForDays  <br/> |Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias (aproximadamente 7 anos).  <br/> |60 dias  <br/> |
|KeepErrorReportForDays  <br/> |Indica o número de dias durante os quais esses relatórios de erro CDR serão mantidos; quaisquer relatórios mais antigos do que o número especificado de dias serão automaticamente excluídos. Os relatórios de erro de CDR são relatórios de diagnóstico carregados por aplicativos cliente, como Skype for Business Server.  <br/> É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se o monitoramento de QoE está habilitado ou não. Se for Verdadeiro, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.  <br/> |Verdadeiro  <br/> |
|EnablePurging  <br/> |Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.  <br/> |Verdadeiro  <br/> |
|KeepQoEDataForDays  <br/> |Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration. Por exemplo, esse comando (executado de dentro do Shell de Gerenciamento Skype for Business Server) desabilita o monitoramento de CDR no escopo global; isso é feito definindo a propriedade EnableCDR como False ($False):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Observe que a desabilitação do monitoramento não desassocia o repositório de monitoramento do pool Front-End, nem desinstala ou afeta de outra forma o banco de dados de monitoramento backend. Quando você usa Skype for Business Server Shell de Gerenciamento para desabilitar o monitoramento de CDR ou QoE, tudo o que você realmente faz é interromper temporariamente Skype for Business Server de coletar e arquivar dados de monitoramento. Se quiser continuar, nesse caso, a coleta e o arquivamento de dados CDR, tudo o que você precisa fazer é definir a propriedade EnableCDR de volta para Verdadeiro ($True):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Da mesma maneira, esse comando desabilita a exclusão de registros QoE no escopo global:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Além das configurações globais, as configurações de CDR e QoE podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento; por exemplo, um administrador pode habilitar o monitoramento de CDR para o site Redmond, mas desabilitar o monitoramento de CDR para o site Dublin. Para criar novas configurações de CDR no escopo do site, use um comando parecido com o seguinte:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Lembre-se de que as configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o monitoramento CDR esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que as informações de registro de detalhe da chamada não serão arquivadas para usuários no site Redmond. No entanto, usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site Redmond) terão suas informações de registro de detalhe da chamada arquivadas.
  
As novas configurações de QoE podem ser criadas no escopo do site usando um comando como este:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Para obter mais informações, digite os seguintes comandos de dentro do Shell de Gerenciamento Skype for Business Server gerenciamento:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
