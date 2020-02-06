---
title: Planejar políticas de localização para o Skype for Business Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leia este tópico para saber como planejar as políticas de localização de uma implantação de serviços de emergência (E9-1-1) aprimorada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802801"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planejar políticas de localização para o Skype for Business Server
 
Leia este tópico para saber como planejar as políticas de localização de uma implantação de serviços de emergência (E9-1-1) aprimorada no Skype for Business Server Enterprise Voice. 
  
> [!NOTE]
> Agora o Skype for Business Server oferece suporte à configuração de vários números de emergência para um cliente. Se quiser configurar vários números de emergência, você deve seguir as informações em [plano para vários números de emergência no Skype for Business Server](multiple-emergency-numbers.md) e [configurar vários números de emergência no Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Crie políticas de localização usando o painel de controle do Skype for Business ou usando o cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Para obter mais informações, consulte [criar políticas de localização no Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Cada política de local contém as seguintes informações:
  
 **Habilitar E9-1-1**
  
Quando este valor é habilitado, o cliente está habilitado para os serviços de emergência E9-1-1. Quando um cliente é registrado, ele tenta adquirir um local do serviço de informações de localização e inclui as informações de localização como parte de uma chamada de emergência.
  
 **Local**
  
Esta configuração é usada somente quando a opção **Habilitar E9-1-1** está habilitada. 
  
Você pode configurar o **Local ** para definir o comportamento do cliente, como a seguir:   
  
- Definir o valor como **Não** significa que o usuário não receberá uma solicitação de local.
    
- Definir o valor como **Sim** significa que o usuário receberá uma solicitação de local, mas poderá ignorá-la.
    
- Definir o valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação de local e um aviso de isenção de responsabilidade caso tente ignorar a solicitação. De qualquer forma, o usuário pode continuar utilizando o cliente.
    
> [!NOTE]
> O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade.  
  
 **Aviso de Isenção de Responsabilidade do Serviço de Emergência Avançado**
  
Esta configuração especifica o aviso de isenção de responsabilidade que o usuário verá caso ignore a solicitação de local. No Skype for Business Server, você pode usar a política de localização para definir avisos de isenção de responsabilidade diferentes para locais diferentes ou conjuntos de usuários diferentes.
  
 **Cadeia de Discagem de Emergência (número de discagem para E9-1-1)**
  
Esta cadeia de caracteres de discagem (menos a "+" à esquerda, mas incluindo qualquer normalização feita pelo plano de discagem do usuário) significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
  
> [!NOTE]
> Se a sua organização não usar um prefixo de acesso de linha externa, você não precisará criar uma regra de normalização de plano de discagem correspondente que adiciona "+" à cadeia de caracteres do 911 antes de enviar a chamada para o roteamento de saída em um servidor que executa o Skype for Business Server; o "+" será automaticamente precedida pelo cliente Skype for Business como resultado da política de localização. No entanto, se seu site usa um prefixo de acesso externo, você precisa adicionar uma regra de normalização à política de plano de discagem aplicável que retira o prefixo de acesso externo e adiciona o "+". Por exemplo, se a sua localização usa um prefixo de acesso externo de 9 e um usuário discar 9 911 para fazer uma chamada de emergência, o cliente usará sua política de plano de discagem para normalizar isso para + 911 antes que o número discado seja avaliado por rotas no perfil de localização do chamador. 
  
 **Máscaras de Cadeia de Discagem de Emergência (máscara de discagem para E9-1-1)**
  
Uma lista separada por ponto-e-vírgula de cadeias de discagem que é traduzida para a **cadeia de discagem de emergência**especificada Por exemplo, talvez você queira adicionar 112, que é o número do serviço de emergência para a maioria da Europa. Um usuário visitante do Skype for Business da Europa talvez não saiba que 911 é o número de emergência dos EUA, mas pode discar o 112 e obter o mesmo resultado. Assim como na cadeia de caracteres de discagem de emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externos, certifique-se de que haja regras de normalização na política de plano de discagem do usuário para retirar o dígito de código de acesso.
  
 **Uso de PSTN**
  
O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
  
> [!NOTE]
> É possível atribuir apenas um Uso a uma política de local. Esse uso de PSTN substitui os usos de PSTN atribuídos à política de voz do usuário, mas se aplica somente a chamadas feitas à cadeia de discagem de emergência ou a uma das máscaras de cadeia de discagem de emergência. 
  
 **URI de notificação**
  
Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de IM (Sistema de Mensagens Instantâneas) quando uma chamada de emergência for realizada. Há suporte para grupos de distribuição.
  
 **URI de Conferência**
  
Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita.   
  
 **Modo de Conferência**
  
Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias.  
  
 **Intervalo de Atualização de Local**
  
Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de localização do serviço de informações de localização. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.
  

