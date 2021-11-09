---
title: Planejar vários números de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leia este tópico para saber como planejar vários números de emergência Skype for Business Server.
ms.openlocfilehash: fbff70b3772b9d941d615f3d1aaf2ad668177e30
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861128"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planejar vários números de emergência no Skype for Business Server
 
Leia este tópico para saber como planejar vários números de emergência Skype for Business Server.
  
Skype for Business Server agora suporta a configuração de vários números de emergência para um cliente. Vários números de emergência é um novo recurso introduzido na Atualização Cumulativa de junho de 2016. Embora os Estados Unidos tenha um único número de emergência, 911, muitos países suportam vários números de emergência. O Reino Unido, por exemplo, dá suporte a 999, o número de emergência específico do Reino Unido, e 112, o número de emergência para a União Europeia. 
  
Esse recurso também é útil para provedores de saúde nos Estados Unidos que querem ter suporte móvel para vários números de emergência azul de código.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Vários números de emergência e políticas de localização

Configure a chamada de emergência criando políticas de local que definem como a chamada de emergência será implementada. Você usa a política de local para definir qual número constitui uma chamada de emergência, por exemplo, 911 nos Estados Unidos; 999 e 112 no Reino Unido. A política de local determina se um usuário está habilitado para chamada de emergência e, em caso afirmativo, qual é o comportamento de uma chamada de emergência. Você também pode definir se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser roteada.
  
Para obter mais informações sobre como definir e modificar uma política de local, consulte [Plan location policies for Skype for Business Server](location-policies.md) and Create location policies in [Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Estes tópicos descrevem conceitos sobre políticas de localização; no entanto, você deve seguir as instruções em [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar vários números de emergência.
  
Ao planejar vários números de emergência, lembre-se do seguinte:
  
- Com a Atualização Cumulativa de junho de 2016, você pode definir até 5 números de emergência para uma determinada política de local. Com a Atualização Cumulativa de novembro de 2016, esse número aumenta para 100.
    
    > [!NOTE]
    > Se você ainda não tiver atualizado para a Atualização Cumulativa de novembro de 2016, consulte [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência, que são exclusivas de uma determinada política de local.
    
    Uma máscara de discagem é um número que você deseja traduzir para o valor do valor do número de discagem de emergência quando ela é discada. Por exemplo, suponha que você insira um valor 212 neste campo e que o campo número de discagem de emergência tenha um valor 911. Quando um usuário disca 212, o número será convertido para 911. Isso permite que números de emergência alternativos sejam discados e ainda assim a chamada chegue aos serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar o número desse país ou região em vez do número do país ou região em que está no momento). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O limite de cadeia de caracteres para uma máscara de discagem é de 100 caracteres. Cada caractere deve ser um dígito entre 0 e 9.
    
- Cada política de local tem um único uso de PSTN (rede telefônica pública comutado) que é usado para determinar qual rota de voz é usada para rotear chamadas de emergência de clientes que usam essa política. O uso pode ter uma rota exclusiva por número de emergência.
    
- Se uma política de local tiver os parâmetros EmergencyNumbers e DialString definidos e o cliente suportar vários números de emergência, o número de emergência terá precedência. Se o cliente não suportar vários números de emergência, a cadeia de caracteres de discagem de emergência será usada.
    
- Para obter informações sobre quais clientes Skype for Business e Lync suportam receber vários números de emergência, máscaras de discagem e usos de PSTN (rede telefônica pública comutado), consulte Suporte ao [cliente](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Não é possível configurar vários números de emergência usando o painel Skype for Business Controle. Você deve usar o PowerShell para configurar vários números de emergência. 
  
Antes de configurar vários números de emergência, lembre-se do seguinte:
  
- Para configurar vários números de emergência, você deve usar o cmdlet New-CsEmergencyNumber e definir políticas de localização que suportam mais de um número de emergência especificando o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)
    
- Se você tiver números existentes definidos usando o cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask, os valores especificados com o parâmetro EmergencyNumbers terão precedência sobre os valores antigos. Ou seja, os valores dos parâmetros EmergencyDialString e EmergencyDialMask serão ignorados.
    
- Se você tiver números existentes definidos usando o cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask e não configurar novos números de  *emergência,*  os números existentes continuarão a ser usados.
    
- Para que o recurso de vários números de emergência funcione, as versões do cliente que você está executando devem ser capazes de dar suporte ao novo recurso. Os clientes mais antigos continuarão a usar os valores antigos especificados pelos cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask. 
    
- Se os usuários discarem um número que corresponde à cadeia de caracteres de discagem, nenhuma máscara de discagem será necessária. Por exemplo, se o número que um usuário disca for 911, a cadeia de caracteres de discagem será 911 e nenhuma máscara será necessária. 
    
Para obter mais informações sobre como configurar vários números de emergência, consulte [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
A tabela a seguir mostra políticas de local de exemplo (para fins do exemplo, nem todos os atributos são mostrados):
  

|**Nome da política de local**|**E911 habilitado**|**Cadeia de caracteres de discagem de emergência**|**Máscara de discagem**|**Números de emergência**|**Uso de PSTN**|**Local necessário**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sim  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Sim  <br/> |
|US-Hospital  <br/> |Sim  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sim  <br/> |
|Londres  <br/> |Sim  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |Não  <br/> |
|Índia  <br/> |Sim  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Não  <br/> |
   
 **Estados Unidos** — Não há requisito para vários números de emergência. Nos Estados Unidos, você usa as configurações antigas de Cadeia de Discagem de Emergência e Máscara de Discagem.
  
 **US-Hospital** — Há um requisito para não mascarar "450". Para clientes que ainda não suportam vários números de emergência, você pode usar as configurações antiga de Cadeia de Discagem de Emergência e Máscara de Discagem. Para clientes que suportam vários números de emergência, você pode definir um número de emergência para "911" e "450" em vez de mascarar 450.
  
 **Londres** — Para clientes que ainda não suportam vários números de emergência, você pode usar as configurações antiga de Cadeia de Discagem de Emergência e Máscara de Discagem. Para clientes que suportam vários números de emergência, você pode definir um número de emergência para "999" e "112" com máscaras para cada um.
  
 **Índia** — Todos os clientes implantados suportam vários números de emergência. Na Índia, você só precisa configurar vários números de emergência.
  
## <a name="client-support"></a>Suporte ao cliente
<a name="BKMK_Clients"> </a>

A tabela a seguir mostra o suporte do cliente para vários números de emergência. A Microsoft continuará a testar e liberar suporte para clientes adicionais. Verifique novamente com frequência.

|**Windows**|**Versão**|
|:-----|:-----|
|**Clique para Executar** <br/> |CC (Canal Atual) lançado em 10 de maio de 2016 - Versão 1604 (Build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) lançado em 14 de junho de 2016 - Versão 1605 (Build 6965.2058)  <br/> |
||DC (Canal Adiado) lançado em 11 de outubro de 2016 - Versão 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Atualização de 7 de junho - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versão** <br/> |
||Skype for Business Mac client versão 16.9  <br/> Skype for Business cliente iOS versão 6.16  <br/> |
|**Android** <br/> |**Versão** <br/> |
||Skype for Business Versão 6.17 do cliente Android  <br/> |
|**Lync Phone Edition** <br/> |**Versão** <br/> |
|| Telefones Aastra 6721ip e Aastra 6725ip - atualização cumulativa de setembro de 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Telefones HP 4110 e HP 4120 - atualização cumulativa de setembro de 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Telefones Polycom CX500, Polycom CX600 e Polycom CX3000 - Atualização cumulativa de setembro de 2016 (Build 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
