---
title: Planejar para vários números de emergências Skype Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leia este tópico para saber como planejar para vários números de emergências Skype Business Server.
ms.openlocfilehash: e3ecbc039dac510a1ebc5eb989773c1f32c3b6ac
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880760"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planejar para vários números de emergências Skype Business Server
 
Leia este tópico para saber como planejar para vários números de emergências Skype Business Server.
  
Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente. Vários números de emergência são um novo recurso introduzido no de 2016 junho atualizações cumulativas. Enquanto os Estados Unidos têm um único número de emergência (911), muitos países dão suporte a vários números de emergência. Reino Unido, por exemplo, oferece suporte a 999, o número de emergência específico para o Reino Unido e o 112, o número de emergência União Europeia. 
  
Esse recurso também é útil para os prestadores de serviços de saúde nos Estados Unidos que querem ter suporte de roaming para vários números de emergência de código azul.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Vários números de emergência e políticas de local

Você configurar chamadas de emergência criando políticas de local que definem como as chamadas de emergência serão implementadas. Você usar a diretiva de local para definir qual número constitui uma chamada de emergência — por exemplo, 911 nos Estados Unidos; 999 e 112 no Reino Unido. A política de local determina se um usuário está habilitado para chamadas de emergência e, nesse caso, qual é o comportamento de uma chamada de emergência. Você também pode definir se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.
  
Para obter mais informações sobre como definir e modificar uma política de local, consulte [planejar políticas de local para Skype para Business Server](location-policies.md) e [criar políticas de local no Skype para Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Estes tópicos descrevem os conceitos sobre políticas de local; No entanto, você deve seguir as instruções em [Configurar vários números de emergências Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar vários números de emergências.
  
Ao planejar vários números de emergência, tenha em mente o seguinte:
  
- Com o de 2016 junho atualização cumulativa, você pode definir até 5 números de emergências para uma política de local determinado. Com o de 2016 novembro atualização cumulativa, esse número aumenta a 100.
    
    > [!NOTE]
    > Se você ainda não atualizadas para o de 2016 novembro atualização cumulativa, consulte [atualizações para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência, que são exclusivas de uma política de local determinado.
    
    Uma máscara de discagem é um número que você deseja converter no valor do número de discagem de emergência quando ela for discada. Por exemplo, suponha que você digite um valor 212 nesse campo e o botão de número de emergência tenha o valor 911. Quando um usuário discar 212, o número será convertido em 911. Isso permite a números de emergências alternativos para ser discado e ainda têm a chamada acessar os serviços de emergências (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar que o país ou região de número, e não o número para o país ou região que estiverem em). É possível definir várias máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O limite de cadeia de caracteres para uma máscara de discagem é de 100 caracteres. Cada caractere deve ser um dígito de 0 a 9.
    
- Cada política de local tem um único uso de PSTN (rede telefônica pública comutada), que é adotado para determinar qual rota de voz é utilizada para rotear chamadas de emergência de clientes que usam essa política. O uso pode ter uma única rota por número de emergência.
    
- Se uma política de local tiver os parâmetros EmergencyNumbers e DialString definidos, e o cliente der suporte a vários números de emergência, o número de emergência terá precedência. Se o cliente não der suporte a vários números de emergência, a cadeia de caracteres de discagem de emergência será usada.
    
- Para obter informações sobre qual Skype para negócios e Lync clientes receber vários números de emergências de suporte, máscaras e usos do telefônica pública comutada (PSTN) de rede de discagem, consulte [suporte do cliente](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Você não pode configurar vários números de emergências usando o Skype para painel de controle de negócios. Use o PowerShell para configurar vários números de emergência. 
  
Antes de configurar vários números de emergência, lembre-se do seguinte:
  
- Para configurar vários números de emergências, você deve usar o cmdlet New-CsEmergencyNumber, e você deve definir políticas de local que oferecem suporte a mais de um número de emergência, especificando o parâmetro EmergencyNumbers com o [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e Cmdlets [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- 	Se houver números existentes definidos usando os cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask, os valores especificados com o parâmetro EmergencyNumbers terão precedência sobre os valores antigos. Ou seja, os valores dos parâmetros EmergencyDialString e EmergencyDialMask serão ignorados.
    
- Se você tiver os números existentes definidos usando o Set-CsLocationPolicy ou o cmdlet New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask, *e você não configurar novos números de emergências* , os números existentes continuarão a ser usado.
    
- Para que o recurso de vários números de emergência funcione, as versões do cliente em execução devem dar suporte ao novo recurso. Os clientes mais antigos continuarão usando os valores antigos especificados pelos cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask. 
    
- Se os usuários forem discar um número correspondente à cadeia de caracteres de discagem, não será necessária uma máscara de discagem. Por exemplo, se o número que um usuário disca é 911, a cadeia de caracteres de discagem é 911 e a máscara não é necessária. 
    
Para obter mais informações sobre como configurar vários números de emergências, consulte [Configure números de emergência vários em Skype para negócios](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
A tabela a seguir mostra exemplos de políticas de local (nem todos os atributos são mostrados):
  

|**Nome da política de local**|**E911 habilitado**|**Cadeia de discagem de emergência**|**Máscara de discagem**|**Números de emergência**|**Uso de PSTN**|**Local necessário**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sim  <br/> |911  
  <br/> | 112;999 <br/> ||USEmergency  <br/> |Sim  <br/> |
|US-Hospital  <br/> |Sim  <br/> |911  
  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sim  <br/> |
|Londres  <br/> |Sim  <br/> |999  
  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |Não  <br/> |
|Índia  <br/> |Sim  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Não  <br/> |
   
 **Estados Unidos** — não há nenhum requisito para vários números de emergências. Nos Estados Unidos, você deve usar as configurações de cadeia de caracteres de discagem de emergência e de máscara de discagem antigas.
  
 **US hospitais** — houver um requisito para não mascarar "450". Para clientes que ainda não aceitam vários números de emergências, você pode usar as configurações de emergência cadeia de caracteres de discagem e discagem máscara antigas. Para clientes que oferecem suporte a vários números de emergências, é possível definir um número de emergência para "911" e "450", em vez de mascaramento 450.
  
 **Londres** — para clientes que ainda não aceitam vários números de emergências, você pode usar as configurações de emergência cadeia de caracteres de discagem e discagem máscara antigas. Para clientes que oferecem suporte a vários números de emergências, é possível definir um número de emergência para "999" e "112" com máscaras para cada um.
  
 **Índia** — todos os clientes implantados oferecem suporte a vários números de emergências. Na Índia, você só precisará configurar vários números de emergências.
  
## <a name="client-support"></a>Suporte ao cliente
<a name="BKMK_Clients"> </a>

A tabela a seguir mostra o suporte do cliente para vários números de emergência. A Microsoft continuará a testar e liberar suporte para clientes adicionais. Confira regularmente.

|**Windows**|**Versão**|
|:-----|:-----|
|**Clique para Executar** <br/> |CC (canal atual) lançados em 10 de maio de 2016 - 1604 versão (Build 6868.2062)  <br/> |
||FRDC (Canal Atual de Primeiro Lançamento) lançado em 14 de junho de 2016 - versão 1605 (Build 6965.2058)  <br/> |
||DC (Canal Adiado) lançado em 11 de outubro de 2016 - Versão 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Atualização de 7 de junho-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versão** <br/> |
||Skype para Mac Business 16,9 da versão do cliente  <br/> Skype para negócios iOS versão de cliente 6.16  <br/> |
|**Android** <br/> |**Versão** <br/> |
||Skype para negócios Android versão de cliente 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Versão** <br/> |
|| Aastra 6721ip e telefones do Aastra 6725ip - setembro de 2016 cumulativa atualizar (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| Telefones HP 4110 e HP 4120 - atualização cumulativa de setembro de 2016 (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Telefones Polycom CX500, Polycom CX600 e Polycom CX3000 - atualização cumulativa de setembro de 2016 (Build 7577.4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

