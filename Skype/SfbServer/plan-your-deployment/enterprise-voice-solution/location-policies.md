---
title: Planejar políticas de local para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência aprimorados (E9-1-1) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825531"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planejar políticas de local para o Skype for Business Server
 
Leia este tópico para saber como planejar políticas de local para uma implantação de serviços de emergência aprimorados (E9-1-1) no Skype for Business Server Enterprise Voice. 
  
> [!NOTE]
> O Skype for Business Server agora dá suporte à configuração de vários números de emergência para um cliente. Se você quiser configurar vários números de emergência, siga as informações no Plano para vários números de emergência no [Skype for Business Server](multiple-emergency-numbers.md) e configure vários números de emergência no Skype for [Business.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 
  
Crie políticas de local usando o Painel de Controle do Skype for Business ou o cmdlet [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Para obter mais informações, [consulte Criar políticas de local no Skype for Business Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)
  
Cada política de local contém as seguintes informações:
  
 **Habilitar 9-1-1 Enhanced**
  
Quando esse valor está habilitado, o cliente é habilitado para serviços de emergência aprimorados (E9-1-1). Quando um cliente se registra, ele tenta adquirir um local do serviço de Informações de Local e inclui as informações de local como parte de uma chamada de emergência.
  
 **Location**
  
Essa configuração é usada somente **quando a opção Habilitar 9-1-1 está** habilitada.
  
Você pode definir a **configuração** Local para definir o comportamento do cliente da seguinte forma:
  
- A definição do valor como **Não** significa que o usuário não receberá uma solicitação de local.
    
- A definição do valor como **Sim** significa que o usuário receberá uma solicitação por um local, mas poderá ignorar a solicitação.
    
- A definição do valor como **Aviso de isenção de responsabilidade** significa que o usuário receberá uma solicitação por um local e mostrará um aviso de isenção de responsabilidade caso ele tente ignorar a solicitação. Em todos os casos, o usuário pode continuar a usar o cliente.
    
> [!NOTE]
> O texto do aviso de isenção de responsabilidade não aparecerá se um usuário inserir manualmente um local antes de ser habilitado para E9-1-1. As atualizações para o texto do aviso de isenção de responsabilidade não será visualizado pelos usuários que já visualizaram o aviso de isenção de responsabilidade. 
  
 **Isenção de Responsabilidade do Serviço de Emergência Avançado**
  
Esta configuração especifica o aviso de isenção que o usuário ver se ignorar o aviso em um local. No Skype for Business Server, você pode usar a política de local para definir avisos de isenção de responsabilidade diferentes para localidades diferentes ou conjuntos diferentes de usuários.
  
 **Sequência de discagem de emergência (número de discagem de E9-1-1)**
  
Essa cadeia de caracteres de discagem (menos o "+" à frente, mas incluindo qualquer normalização feita pelo Plano de Discagem do usuário) significa que uma chamada é uma chamada de emergência. A **Sequência de discagem de emergência** faz com que o cliente inclua na chamada informações sobre o local e sobre retorno de chamada.
  
> [!NOTE]
> Se sua organização não usar um prefixo de acesso de linha externa, não será necessário criar uma regra de normalização do Plano de Discagem correspondente que adiciona um "+" à cadeia de caracteres 911 antes de enviar a chamada para o Roteamento de Saída em um servidor que executa o Skype for Business Server; o "+" será automaticamente anexado pelo cliente Skype for Business como resultado da política de local. No entanto, se o seu site usa um prefixo de acesso externo, você precisa adicionar uma regra de normalização à política de Plano de Discagem aplicável que retira o prefixo de acesso externo e adiciona o "+". Por exemplo, se o seu local usa um prefixo de acesso externo de 9 e um usuário disca 9 911 para fazer uma chamada de emergência, o cliente usará sua política de Plano de Discagem para normalizá-lo para +911 antes que o número discado seja avaliado pelas rotas no perfil de local do chamador. 
  
 **Máscaras de sequência de discagem de emergência (máscara de discagem E9-1-1)**
  
Uma lista separada por ponto e vírgula de sequências de discagem a serem traduzidas para a **Sequência de discagem de emergência**. Por exemplo, você pode querer adicionar 112, que é o número do serviço de emergência em grande parte da Europa. Um usuário do Skype for Business visitante da Europa pode não saber que 911 é o número de emergência dos EUA, mas pode discar para 112 e obter o mesmo resultado. Assim como acontece com a cadeia de caracteres de discagem de emergência, não inclua um "+" antes de cada número e, se você usar códigos de acesso de linha externa, certifique-se de que haja regras de normalização na política de Plano de Discagem do usuário para retirar o dígito do código de acesso.
  
 **Uso de PSTN**
  
O nome do Uso de PSTN que contém os caminhos de roteamento que determinam para qual tronco SIP, gateway PSTN ou gateway ELIN as chamadas serão encaminhadas.
  
> [!NOTE]
> É possível atribuir apenas um Uso a uma política de local. Esse Uso de PSTN substitui os Usos de PSTN atribuídos à política de voz do usuário, mas só se aplica a chamadas feitas para a cadeia de caracteres de discagem de emergência ou para uma das Máscaras de Sequência de Discagem de Emergência. 
  
 **URI de notificação**
  
Especifica um ou mais URIs SIP do pessoal de segurança que receberá uma notificação de mensagem instantânea (IM) quando uma chamada de emergência for realizada. Os grupos de distribuição são suportados.
  
 **URI de conferência**
  
Especifica um número DID (discagem direta interna) (normalmente um número do suporte de segurança) que deve ser verificado quando uma chamada de emergência é feita. 
  
 **Modo de conferência**
  
Especifica se o URI de conferência será inserido na chamada de emergência usando comunicação de uma ou duas vias. 
  
 **Intervalo de atualização de local**
  
Especifica a quantidade de tempo (em horas) entre as solicitações do cliente para uma atualização de local do serviço de Informações de Local. O valor pode ser definido para qualquer valor entre 1 e 12. O valor padrão é 4.
  

