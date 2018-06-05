---
title: Configurar o registro de detalhes de chamada e configurações de qualidade da experiência no Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumo: Saiba como configurar o CDR e QoE no Skype para Business Server 2015.'
ms.openlocfilehash: 0d5a6ba25a524578a13f16c92149977b0180fbdb
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569453"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server-2015"></a>Configurar o registro de detalhes de chamada e configurações de qualidade da experiência no Skype para Business Server 2015
 
**Resumo:** Saiba como configurar o CDR e QoE no Skype para Business Server 2015.
  
Configure o CDR e QoE monitoring usando relatórios do SQL Server Reporting Services para Skype para Business Server 2015.
  
## <a name="configure-cdr-and-qoe"></a>Configurar o CDR e QoE

Depois que você tiver associado a um repositório de monitoramento com um pool de Front-End, configure o repositório de monitoramento e, em seguida, instalado e configurado do SQL Server Reporting Services e relatórios de monitoramento você pode gerenciar a gravação de detalhes das chamadas (CDR) e Quality of Experience (QoE) Monitorando usando Skype do Shell de gerenciamento do servidor de negócios. Skype para cmdlets do Shell de gerenciamento do Business Server permitem que você habilitar e desabilitar o CDR e/ou QoE monitoring para um site específico ou para seu Skype toda a implantação de servidor de negócios; que pode ser feito com um comando simple, como esta:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Quando você instala o Skype para Business Server 2015, também instalará um conjunto predefinido de definições de configuração global de CDR e QoE. Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se o CDR está habilitado ou não. Se for True, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2.562 dias (aproximadamente sete anos).  <br/> |60 dias  <br/> |
|KeepErrorReportForDays  <br/> |Indica o número de dias que os relatórios de erros de CDR são mantidos; todos os relatórios mais antigos do que o número de dias especificado serão excluídos automaticamente. Relatórios de erros de CDR são relatórios de diagnósticos, carregados por aplicativos de cliente, como Skype para Business Server 2015.  <br/> É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:
  
|**Propriedade**|**Descrição**|**Valor padrão**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se o monitoramento de QoE está habilitado ou não. Se for True, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.  <br/> KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.  <br/> |60 dias  <br/> |
   
Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration. Por exemplo, este comando (executado de dentro do Skype do Shell de gerenciamento do servidor de negócios) desabilita CDR monitoring no escopo global; Isso é feito definindo a propriedade EnableCDR como False ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Observe que desabilitar o monitoramento não desassocia o repositório de monitoramento do pool de Front-Ends, nem desinstala ou afeta o banco de dados de monitoramento back-end. Quando você usa o Skype para Business Server Management Shell para desabilitar o CDR ou QoE monitoring tudo o que você realmente fazer é interromper temporariamente Skype para Business Server da coleta e monitoramento de dados de arquivamento. Se você quiser, nesse caso, continuar a coleta e o arquivamento de dados CDR, tudo o que precisa fazer é definir a propriedade EnableCDR de volta para True ($True):
  
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

Para obter mais informações, digite os comandos a seguir de dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```