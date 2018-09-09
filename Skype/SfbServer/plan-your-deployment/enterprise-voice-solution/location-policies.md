---
title: Planejar políticas de local Skype for Business Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência avançado (E9-1-1) no Skype Business Server Enterprise Voice.
ms.openlocfilehash: 919a09bb907bda8666c9a44ee61436643a912d61
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887320"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planejar políticas de local Skype for Business Server
 
Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência avançado (E9-1-1) no Skype Business Server Enterprise Voice. 
  
> [!NOTE]
> Skype para Business Server agora oferece suporte a configuração de vários números de emergências para um cliente. Se você deseja configurar vários números de emergências, você deve seguir as informações em [vários números de emergências Skype para Business Server planejar](multiple-emergency-numbers.md) e [Configurar vários números de emergências Skype para negócios](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Crie políticas de local usando o Skype para painel de controle corporativos ou usando o cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Para obter mais informações, consulte [criar políticas de local no Skype para Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada política de local contém as seguintes informações:
  
 **Habilitar E9-1-1**
  
Quando este valor é habilitado, o cliente está habilitado para os serviços de emergência E9-1-1. Quando um cliente registra, ele tenta adquirir uma localização do serviço de informações de local e incluirá as informações de localização como parte de uma chamada de emergência.
  
 **Local**
  
Esta configuração é usada somente quando a opção **Habilitar E9-1-1** está habilitada. 
  
Você pode configurar o **Local ** para definir o comportamento do cliente, como a seguir:   
  
- Definir o valor como **Não** significa que o usuário não receberá uma solicitação de local.
    
- Definir o valor como **Sim** significa que o usuário receberá uma solicitação de local, mas poderá ignorá-la.
    
- Definir o valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação de local e um aviso de isenção de responsabilidade caso tente ignorar a solicitação. De qualquer forma, o usuário pode continuar utilizando o cliente.
    
> [!NOTE]
> O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade.  
  
 **Aviso de Isenção de Responsabilidade do Serviço de Emergência Avançado**
  
Esta configuração especifica o aviso de isenção de responsabilidade que o usuário verá caso ignore a solicitação de local. No Skype para Business Server, você pode usar a política de local para definir avisos de isenção diferentes para diferentes grupos de usuários ou de diferentes localidades.
  
 **Cadeia de Discagem de Emergência (número de discagem para E9-1-1)**
  
Esta cadeia de caracteres de discagem (menos o prefixo "+", mas incluindo qualquer normalização feita pelo plano de discagem do usuário) significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
  
> [!NOTE]
> Se sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma correspondente plano de discagem da regra de normalização que adiciona um "+" para a cadeia de caracteres 911 antes de enviar a chamada para o roteamento de saída em um servidor executando o Skype para Business Server; o "+" será colocada automaticamente antes pelo Skype para clientes corporativos como resultado a política de local. No entanto, se o seu site usa um prefixo de acesso externo, você precisará adicionar uma regra de normalização para a política de plano de discagem aplicável que retira o prefixo de acesso externo e adiciona o "+". Por exemplo, se seu local usa um prefixo de acesso externo de 9 e um usuário disca 9 911 para colocar uma chamada de emergência, o cliente usará sua política de plano de discagem normalizar isso para +911 antes do número discado é avaliado com as rotas no perfil da localidade do chamador. 
  
 **Máscaras de Cadeia de Discagem de Emergência (máscara de discagem para E9-1-1)**
  
Uma-vírgula lista de cadeias de caracteres de discagem que é convertida em **Cadeia de caracteres de discagem de emergência**especificada. Por exemplo, convém adicionar 112, que é o número de serviço de emergência para a maioria dos Europa. Um visitante Skype para o usuário de negócios da Europa talvez não saiba que 911 é o número de emergência EUA, mas eles possam discar 112 e obter o mesmo resultado. Conforme com a cadeia de caracteres de discagem de emergência, não incluir um "+" antes de cada número, e se você usar códigos de acesso de linha externa, certifique-se de que há regras de normalização na política de plano de discagem do usuário para retirar desativa o dígito do código de acesso.
  
 **Uso de PSTN**
  
O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
  
> [!NOTE]
> É possível atribuir apenas um Uso a uma política de local. Este uso de PSTN substitui os usos da PSTN atribuídos à política de voz do usuário, mas se aplica somente às chamadas feitas para a cadeia de caracteres de discagem de emergência ou para uma das máscaras de cadeia de caracteres de discagem de emergência. 
  
 **URI de notificação**
  
Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de IM (Sistema de Mensagens Instantâneas) quando uma chamada de emergência for realizada. Há suporte para grupos de distribuição.
  
 **URI de Conferência**
  
Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.   
  
 **Modo de Conferência**
  
Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias.  
  
 **Intervalo de Atualização de Local**
  
Especifica a quantidade de tempo (em horas) entre as solicitações de cliente para uma atualização local do serviço de informações de local. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.
  

