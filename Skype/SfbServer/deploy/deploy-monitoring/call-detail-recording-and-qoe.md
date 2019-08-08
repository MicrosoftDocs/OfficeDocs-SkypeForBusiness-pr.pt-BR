---
title: Configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumo: saiba como configurar CDR e QoE no Skype for Business Server.'
ms.openlocfilehash: d2f86654e852a2126fc611e820f95b8ebad5259a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239957"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência no Skype for Business Server
 
**Resumo:** Saiba como configurar CDR e QoE no Skype for Business Server.
  
Configurar o monitoramento de CDR e QoE usando relatórios do SQL Server Reporting Services para o Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurar o CDR e QoE

Depois de associar um repositório de monitoramento a um pool de front-end, configurar o repositório de monitoramento e, em seguida, instalar e configurar os relatórios do SQL Server Reporting Services e do monitoramento, você pode gerenciar a CDR (gravação de detalhes de chamadas) e a qualidade da experiência (QoE) monitorando usando o Shell de gerenciamento do Skype for Business Server. Os cmdlets do Shell de gerenciamento do Skype for Business Server permitem habilitar e desabilitar o monitoramento CDR e/ou QoE para um determinado site ou para toda a implantação do Skype for Business Server; Isso pode ser feito com um comando tão simples quanto isto:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Ao instalar o Skype for Business Server, você também instalará uma coleção predefinida de configurações globais de configuração para CDR e QoE. Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se o CDR está habilitado ou não. Se for True, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2.562 dias (aproximadamente sete anos).  <br/> |60 dias  <br/> |
|KeepErrorReportForDays  <br/> |Indica o número de dias durante os quais os relatórios de erro do CDR são mantidos; todos os relatórios anteriores ao número de dias especificado serão excluídos automaticamente. Os relatórios de erro CDR são relatórios de diagnóstico carregados por aplicativos cliente, como o Skype for Business Server.  <br/> É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se o monitoramento de QoE está habilitado ou não. Se for True, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration. Por exemplo, esse comando (executado no Shell de gerenciamento do Skype for Business Server) desabilita o monitoramento de CDR no escopo global; Isso é feito definindo a propriedade EnableCDR como false ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Observe que desabilitar o monitoramento não desassocia o repositório de monitoramento do pool de Front-Ends, nem desinstala ou afeta o banco de dados de monitoramento back-end. Quando você usa o Shell de gerenciamento do Skype for Business Server para desabilitar o monitoramento de CDR ou QoE, você realmente interrompe o Skype for Business Server temporariamente de coletar e arquivar dados de monitoramento. Se você quiser, nesse caso, continuar a coleta e o arquivamento de dados CDR, tudo o que precisa fazer é definir a propriedade EnableCDR de volta para True ($True):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Da mesma maneira, esse comando desabilita a exclusão de registros QoE no escopo global:
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Além das configurações globais, as configurações de CDR e QoE podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento; por exemplo, um administrador pode habilitar o monitoramento de CDR para o site Redmond, mas desabilitar o monitoramento de CDR para o site Dublin. Para criar novas configurações de CDR no escopo do site, use um comando parecido com o seguinte:
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Lembre-se de que as configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o monitoramento CDR esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que as informações de registro de detalhe da chamada não serão arquivadas para usuários no site Redmond. No entanto, usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site Redmond) terão suas informações de registro de detalhe da chamada arquivadas.
  
As novas configurações de QoE podem ser criadas no escopo do site usando um comando como este:
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Para obter mais informações, digite os seguintes comandos no Shell de gerenciamento do Skype for Business Server:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
