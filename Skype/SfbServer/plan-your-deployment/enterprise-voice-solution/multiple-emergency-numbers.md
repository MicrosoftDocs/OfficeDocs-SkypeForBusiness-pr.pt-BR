---
title: Planejar vários números de emergência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leia este tópico para saber como planejar vários números de emergência no Skype for Business Server.
ms.openlocfilehash: 10b6d02391fbf1ac7af1ae5233261c36fd2fd6ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983016"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Planejar vários números de emergência no Skype for Business Server
 
Leia este tópico para saber como planejar vários números de emergência no Skype for Business Server.
  
O Skype for Business Server agora oferece suporte à configuração de vários números de emergência para um cliente. Vários números de emergência são um novo recurso introduzido na atualização cumulativa de junho de 2016. Enquanto os Estados Unidos têm um único número de emergência, 911, muitos países suportam vários números de emergência. O Reino Unido, por exemplo, oferece suporte a ambos os 999, o número de emergência específico para o Reino Unido e 112, o número de emergência da União Européia. 
  
Esse recurso também é útil para os provedores de assistência médica nos Estados Unidos que desejam ter suporte de roaming para vários números de emergência azuis de código.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Vários números de emergência e políticas de local

Você configura a chamada de emergência criando políticas de local que definem como a chamada de emergência será implementada. Use a política de local para definir o número que constitui uma chamada de emergência — por exemplo, 911 nos Estados Unidos; 999 e 112 no Reino Unido. A política de local determina se um usuário está habilitado para chamadas de emergência e, em caso afirmativo, qual é o comportamento de uma chamada de emergência. Você também pode definir se a segurança corporativa deve ser notificada automaticamente e como a chamada deve ser encaminhada.
  
Para obter mais informações sobre como definir e modificar uma política de local, consulte [Plan Location Policies for Skype for Business Server](location-policies.md) e [Create Location Policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Estes tópicos descrevem conceitos sobre políticas de local; no entanto, você deve seguir as instruções em [configurar vários números de emergência no Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) para configurar vários números de emergência.
  
Ao planejar vários números de emergência, lembre-se do seguinte:
  
- Com a atualização cumulativa de junho de 2016, você pode definir até 5 números de emergência para uma determinada política de local. Com a atualização cumulativa de novembro de 2016, esse número aumenta para 100.
    
    > [!NOTE]
    > Se você ainda não tiver atualizado para a atualização cumulativa de novembro de 2016, consulte [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Para cada número de emergência, você pode especificar zero ou mais máscaras de discagem de emergência, que são exclusivas de uma determinada política de local.
    
    Uma máscara de discagem é um número que você deseja converter no valor do valor do número de discagem de emergência quando for discado. Por exemplo, suponha que você insira um valor de 212 neste campo e o campo número de discagem de emergência tenha um valor de 911. Quando um usuário disca 212, o número será convertido em 911. Isso permite que números de emergência alternativos sejam discados e ainda tenham o serviço de emergência de atendimento de chamada (por exemplo, se alguém de um país ou região com um número de emergência diferente tentar discar o número do país ou da região, em vez do número da país ou região em que estão no momento). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O limite de cadeia de caracteres para uma máscara de discagem é de 100 caracteres. Cada caractere deve ser um dígito entre 0 e 9.
    
- Cada política de local tem um único uso de rede telefônica pública comutada (PSTN), que é usada para determinar qual rota de voz é usada para rotear chamadas de emergência de clientes usando esta política. O uso pode ter uma rota exclusiva por número de emergência.
    
- Se uma política de local tiver os parâmetros EmergencyNumbers e dialstring definidos e o cliente oferecer suporte a vários números de emergência, o número de emergência terá prioridade. Se o cliente não oferecer suporte a vários números de emergência, a cadeia de caracteres de discagem de emergência será usada.
    
- Para obter informações sobre quais clientes do Skype for Business e Lync dão suporte ao recebimento de vários números de emergência, máscaras de discagem e usos de PSTN (rede telefônica pública comutada), consulte [suporte ao cliente](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Você não pode configurar vários números de emergência usando o painel de controle do Skype for Business. Você deve usar o PowerShell para configurar vários números de emergência. 
  
Antes de configurar vários números de emergência, lembre-se do seguinte:
  
- Para configurar vários números de emergência, você deve usar o cmdlet New-CsEmergencyNumber e deve definir as políticas de local que dão suporte a mais de um número de emergência especificando o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Se você tiver números existentes definidos usando o cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask, os valores especificados com o parâmetro EmergencyNumbers terão precedência sobre o antigo valores. Ou seja, os valores dos parâmetros EmergencyDialString e EmergencyDialMask serão ignorados.
    
- Se você tiver números existentes definidos usando o cmdlet Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask *e não configurar novos números de emergência* , os números existentes continuarão a ser usados.
    
- Para que o recurso vários números de emergência funcione, as versões do cliente que você está executando devem ser capazes de dar suporte ao novo recurso. Os clientes mais antigos continuarão a usar os valores antigos especificados pelos cmdlets Set-CsLocationPolicy ou New-CsLocationPolicy com os parâmetros EmergencyDialString e EmergencyDialMask. 
    
- Se os usuários forem discar um número que corresponda à cadeia de caracteres de discagem, não será necessária uma máscara de discagem. Por exemplo, se o número que um usuário disca for 911, a cadeia de caracteres de discagem será 911 e nenhuma máscara será necessária. 
    
Para obter mais informações sobre como configurar vários números de emergência, consulte [Configure Multiple Emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
A tabela a seguir mostra exemplos de diretivas de local (para fins do exemplo, nem todos os atributos são mostrados):
  

|**Nome da política de local**|**E911 habilitado**|**Cadeia de discagem de emergência**|**Máscara de discagem**|**Números de emergência**|**Uso de PSTN**|**Local necessário**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Estados Unidos  <br/> |Sim  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sim  <br/> |
|EUA-hospital  <br/> |Sim  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sim  <br/> |
|Londres  <br/> |Sim  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |Não  <br/> |
|Índia  <br/> |Sim  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |Não  <br/> |
   
 **Estados Unidos** — não há requisitos para vários números de emergência. Nos Estados Unidos, você usa a cadeia de caracteres de discagem de emergência antiga e as configurações de máscara de discagem.
  
 **US-hospital** — há um requisito para não mascarar "450". Para clientes que ainda não dão suporte a vários números de emergência, você pode usar a cadeia de caracteres de discagem de emergência e as configurações de máscara de discagem antigas. Para clientes que dão suporte a vários números de emergência, você pode definir um número de emergência para "911" e "450", em vez de mascarar 450.
  
 **London** — para clientes que ainda não dão suporte a vários números de emergência, você pode usar a cadeia de caracteres de discagem de emergência e configurações de máscara de discagem antigas. Para clientes que dão suporte a vários números de emergência, você pode definir um número de emergência para "999" e "112" com máscaras para cada.
  
 **Índia** – todos os clientes implantados dão suporte a vários números de emergência. Na Índia, você só precisa configurar vários números de emergência.
  
## <a name="client-support"></a>Suporte ao cliente
<a name="BKMK_Clients"> </a>

A tabela a seguir mostra o suporte ao cliente para vários números de emergência. A Microsoft continuará a testar e a liberar suporte para clientes adicionais. Verifique novamente com frequência.

|**Windows**|**Versão**|
|:-----|:-----|
|**Clique para Executar** <br/> |CC (canal atual) lançado em 10 de maio de 2016-versão 1604 (Build 6868,2062)  <br/> |
||FRDC (primeiro lançamento do canal atual) lançado em 14 de junho de 2016-versão 1605 (Build 6965,2058)  <br/> |
||DC (canal adiado) lançado em 11 de outubro de 2016-versão 1605 (Build 6965,2092)  <br/> |
|**MSI** <br/> |Atualização de junho de 7-[https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versão** <br/> |
||Cliente Mac do Skype for Business versão 16,9  <br/> Skype for Business iOS Client versão 6,16  <br/> |
|**Android** <br/> |**Versão** <br/> |
||Skype for Business cliente Android versão 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Versão** <br/> |
|| Aastra 6721ip e Aastra 6725ip telefones-atualização cumulativa de setembro de 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| HP 4110 e HP 4120 telefones-atualização cumulativa de setembro de 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 e Polycom CX3000 de telefones-atualização cumulativa de setembro de 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

