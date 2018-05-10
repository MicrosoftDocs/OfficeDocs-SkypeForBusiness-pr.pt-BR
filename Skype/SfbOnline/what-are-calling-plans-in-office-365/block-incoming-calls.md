---
title: Bloquear chamadas de entrada no Skype para negócios Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto: Skype for Business
localization_priority: Normal
ms.custom: Use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: 9a9ff446d7b95588f1d9c2460db1284de717e557
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
 # <a name="block-inbound-calls"></a>Bloquear chamadas de entrada

Skype para negócios Online chamar planos agora oferece suporte a bloqueio de chamadas de entrada da rede telefônica pública comutada (PSTN). Este recurso permite que uma lista global de locatário de padrões de número a ser definida para que a ID de chamadas da PSTN cada entrada chamada para o inquilino pode ser verificada em relação à lista uma correspondência. Se for feita uma correspondência, uma chamada de entrada é rejeitada. 

Esse recurso de bloqueio de chamada de entrada funciona somente em chamadas de entrada provenientes da PSTN e só funciona em uma base de locatário global e não está disponível em uma base por usuário.

Esse recurso ainda não está disponível para roteamento direto.

>[Nota] Chamadores bloqueados perceba ligeiramente diferentes comportamentos quando foram bloqueados. O comportamento será baseado em como operadora do chamador bloqueados trata a notificação de que a chamada não é permitida para ser concluída com êxito. Os exemplos podem incluir uma mensagem de operadora informando que a chamada não pode ser concluída como discado, ou simplesmente ignorar a chamada.

## <a name="call-blocking-admin-controls-and-information"></a>Bloqueando informações e controles de Admin de chamada
São fornecidos controles de administração para números de bloqueio usando apenas o PowerShell. Padrões de bloco de números são definidos como padrões de expressão regular. A ordem das expressões não é importante – o primeiro padrão correspondido na lista resultará na chamada estão sendo bloqueada. Um novo número ou padrão adicionados ou removidos de bloqueios lista de chamadores pode demorar até 24 horas para o padrão para se tornar ativo.
## <a name="call-blocking-powershell-commands"></a>Chamar o bloqueio de comandos do PowerShell

*InboundBlockedNumberPattern* Padrões de número é gerenciado via os comandos *CsInboundBlockedNumberPattern* **New**, **obter**, **Definir**e **Remover**.  

Você pode gerenciar um determinado padrão usando esses cmdlets, incluindo a capacidade de alternar a ativação de um determinado padrão.
- *Get-CsInboundBlockedNumberPattern* Retorna uma lista de todos os padrões de número bloqueados adicionados à lista de locatário, incluindo nome, descrição, Enabled (verdadeiro/falso) e padrão para cada um.
- *New-CsInboundBlockedNumberPattern* Adiciona um padrão de número bloqueado na lista de locatário.
- *Remove-CsInboundBlockedNumberPattern* Remove um padrão de número bloqueado na lista de locatário.
- *Set-CsInboundBlockedNumberPattern* Modifica um ou mais parâmetros de um padrão de número bloqueado na lista de locatário.
- *TenantBlockedCallingNumbers* A exibição e a ativação do recurso de bloqueio de chamada inteira é gerenciada por meio do CsTenantBlockingCallingNumbers comandos obtém e definir. 
- *Get-CsTenantBlockedCallingNumbers* Retorna os parâmetros para a lista global de número bloqueado incluindo Enabled (True/False). Não há uma política de locatário global único que não pode ser modificada manualmente diferente para ativar o recurso completamente ativado/desativado.
- *Set-CsTenantBlockedCallingNumbers* Permite modificar as chamadas de locatário global bloqueado para ser ativado ou desativado no nível do locatário.

### <a name="examples"></a>Exemplos
#### <a name="blocking-a-number"></a>Bloqueando um número

Neste exemplo,-habilitado e - descrição parâmetros são opcionais:

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 Criando que um novo padrão por padrão adicionará o padrão como habilitado e a descrição é sempre e campo opcional para fornecer mais informações. 

É recomendável que você forneça um nome significativo facilmente entender por que o padrão foi adicionado. No caso de spam simplesmente bloqueio números, considerados a regra de nomeação o mesmo como o padrão numérico que está sendo correspondido e adicionar informações adicionais na descrição conforme necessário.

Padrões são comparadas com o uso de expressões regulares (regex). Permitir por tempo de replicação antes de testar e validar.

#### <a name="allowing-a-number"></a>Permitindo que um número

Neste exemplo, o parâmetro identity é necessário:`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
Se a identidade não é conhecida, use o cmdlet *Get-CsInb undBlockedNumberPattern* para localizar primeiro o padrão adequado e anote a identidade. Em seguida, execute o cmdlet *Remove* e passar o valor de identidade apropriado.

Permitir por tempo de replicação antes de testar e validar.
#### <a name="view-all-number-patterns"></a>Exibir todos os padrões de número
A execução deste cmdlet retornará um números da lista de todos os inserido bloqueado para um locatário:`Get-CsInboundBlockedNumberPattern`

Use o PowerShell interno capacidades de filtragem para analisar os valores retornados conforme necessário.

#### <a name="a-note-on-regex"></a>Uma observação sobre Regex
Conforme mencionado anteriormente, o padrão de correspondência para bloquear os chamadores é feito usando expressões regulares (regex). Existem várias ferramentas disponíveis online para ajudar a validar uma correspondência de padrão regex. Se você não estiver familiarizado com os padrões de regex, recomendamos que você leve algum tempo para se familiarizar com os conceitos básicos e para certificar-se de que você obtém os resultados esperados, use uma ferramenta para a validação de padrões correspondentes antes de adicionar novo bloqueado número corresponder ao seu locatário. 

## <a name="related-topics"></a>Tópicos relacionados
[Configure seu computador para Skype para gerenciamento de negócios Online usando o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell )
