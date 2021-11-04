---
title: Planejar políticas de localização para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leia este tópico para saber como planejar políticas de local para uma implantação aprimorada de serviços de emergência (E9-1-1) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: d305d2e453c375616dbba7e077c552372767f2ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762129"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planejar políticas de localização para Skype for Business Server
 
Leia este tópico para saber como planejar políticas de local para uma implantação aprimorada de serviços de emergência (E9-1-1) no Skype for Business Server Enterprise Voice. 
  
> [!NOTE]
> Skype for Business Server agora suporta a configuração de vários números de emergência para um cliente. Se quiser configurar vários números de emergência, siga as informações em Plan for multiple [emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) e Configure multiple emergency numbers in [Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Você cria políticas de localização usando o Painel de Controle Skype for Business ou usando o cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Para obter mais informações, consulte [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada política de local contém as seguintes informações:
  
 **Habilitar o 9-1-1 aprimorado**
  
Quando esse valor é habilitado, o cliente é habilitado para serviços de emergência aprimorados (E9-1-1). Quando um cliente se registra, ele tenta adquirir um local do serviço de Informações de Local e incluirá as informações de local como parte de uma chamada de emergência.
  
 **Localização**
  
Essa configuração é usada somente quando **Enable Enhanced 9-1-1** está habilitado.
  
Você pode configurar a **configuração Local** para definir o comportamento do cliente da seguinte forma:
  
- A definição do valor como **Não** significa que o usuário não receberá uma solicitação de local.
    
- A definição do valor como **Sim** significa que o usuário receberá uma solicitação por um local, mas poderá ignorar a solicitação.
    
- A definição do valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação por um local e mostrará um aviso de isenção de responsabilidade caso ele tente ignorar a solicitação. Em todos os casos, o usuário pode continuar a usar o cliente.
    
> [!NOTE]
> O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade. 
  
 **Isenção de Responsabilidade do Serviço de Emergência Avançado**
  
Esta configuração especifica o aviso de isenção que o usuário ver se ignorar o aviso em um local. Em Skype for Business Server, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou conjuntos diferentes de usuários.
  
 **Cadeia de caracteres de discagem de emergência (número de discagem E9-1-1)**
  
Essa cadeia de caracteres de discagem (menos o "+" principal, mas incluindo qualquer normalização feita pelo Plano de Discagem do usuário) significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
  
> [!NOTE]
> Se sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma regra de normalização correspondente do Plano de Discagem que adiciona um "+" à cadeia de caracteres 911 antes de enviar a chamada para Roteamento de Saída em um servidor que executa Skype for Business Server; o "+" será automaticamente prependido pelo cliente Skype for Business como resultado da política de local. No entanto, se seu site usar um prefixo de acesso externo, você precisará adicionar uma regra de normalização à política de Plano de Discagem aplicável que desmarque o prefixo de acesso externo e adicione o "+". Por exemplo, se sua localização usa um prefixo de acesso externo 9 e um usuário disca 9 911 para fazer uma chamada de emergência, o cliente usará sua política de Plano de Discagem para normalizar isso para +911 antes que o número discado seja avaliado pelas rotas no perfil de localização do chamador. 
  
 **Máscaras de cadeia de caracteres de discagem de emergência (máscara de discagem E9-1-1)**
  
Uma lista separada por ponto e vírgula de sequências de discagem a serem traduzidas para a **Sequência de discagem de emergência**. Por exemplo, você pode querer adicionar 112, que é o número do serviço de emergência em grande parte da Europa. Um usuário Skype for Business de visita da Europa pode não saber que o 911 é o número de emergência dos EUA, mas pode discar 112 e obter o mesmo resultado. Como acontece com a Cadeia de Caracteres de Discagem de Emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externa, certifique-se de que há regras de normalização na política de Plano de Discagem do usuário para desagrecar o dígito do código de acesso.
  
 **Uso de PSTN**
  
O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
  
> [!NOTE]
> É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos PSTN atribuídos à política de voz do usuário, mas se aplica apenas a chamadas feitas à Cadeia de Caracteres de Discagem de Emergência ou a uma das Máscaras de Cadeia de Caracteres de Discagem de Emergência. 
  
 **URI de notificação**
  
Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de mensagem instantânea (IM) quando uma chamada de emergência for realizada. Os grupos de distribuição são suportados.
  
 **URI de conferência**
  
Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita. 
  
 **Modo de conferência**
  
Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias. 
  
 **Intervalo de atualização de local**
  
Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de local do serviço de Informações de Local. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.
