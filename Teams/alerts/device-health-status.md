---
title: Microsoft Teams Monitoramento e alerta de dispositivos
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba como usar os recursos Teams de monitoramento e alerta no centro de administração do Microsoft Teams para monitorar proativamente o estado de saúde dos dispositivos Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336181"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams monitoramento de saúde do dispositivo

O monitoramento de saúde do dispositivo no centro de administração Microsoft Teams oferece a capacidade de monitorar proativamente a saúde de vários Teams dispositivos. Monitore o estado offline de um dispositivo e receba alertas em tempo real se o dispositivo monitorado em sua organização ficar offline.  

Antes de começar, você precisará das permissões de criação de equipes/canal em seu locatário. [Saiba mais](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurar a regra de estado do dispositivo

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Notificações & regras de alertas.**  >  

   ![Seção Regras no Centro de administração](../media/select-rules.png)

2. Na página **Regras,** selecione **Regra de estado do dispositivo**.

3. Selecione o dispositivo para configurar a regra de estado para habilite os alertas.

    ![Teams de regra de estado de dispositivos.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretar a configuração de regra


|Campo |Descrição  |
|--------|-------------|
|**Tipo de regra**   |A regra de estado do dispositivo ajuda você a gerenciar efetivamente. Teams e é classificado como um tipo de gerenciamento de dispositivo. No futuro, mais regras do tipo de gerenciamento de dispositivo estarão disponíveis para monitorar outros recursos relacionados (exemplos podem incluir: dispositivo não aldo e o status de entrada do dispositivo).|
|**Condition**   |Você pode monitorar a saúde dos dispositivos se eles ficarem offline. [Saiba mais sobre](../devices/device-management.md) o gerenciamento de dispositivos Teams centro de administração. |
|**Scope**   |Você pode especificar com que frequência deseja monitorar o status de saúde do dispositivo mencionando a frequência de avaliação de regra. Por padrão, os dispositivos teams serão monitorados em tempo real quase em tempo real se eles ficarem offline. |
|**Usuários do dispositivo**   |Você pode especificar quais dispositivos precisam de monitoramento proativo offline selecionando-os com base em usuários conectados. Consulte [Selecionar dispositivos para obter](#select-devices-for-configuration) mais detalhes. |
|**Ações**  >  **Alerta de canal**   |Na seção Ações, você pode especificar canais de equipe para os quais deseja receber alertas. Atualmente, uma equipe padrão chamada **Alertas** de Administrador e Notificações e canal chamado **MonitoringAlerts** será criado para o qual as notificações serão entregues. <BR/> <BR/> Os administradores globais e Teams administradores em seu locatário serão adicionados automaticamente a essa equipe padrão.|
|**Ações**  >  **Webhook**   |Você também pode receber notificações com um webhook externo (opcional). Especifique uma URL de webhook pública externa na seção webhook onde uma carga de notificação JSON será enviada. <BR/> <BR/>  A carga de notificação, por meio de webhooks, pode ser integrada com outros sistemas em sua organização para criar fluxos de trabalho personalizados.<br/><br/> 

**Esquema de carga JSON para webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Carga JSON de exemplo:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Selecionar dispositivos para configuração

1. Você pode selecionar Teams dispositivos que deseja monitorar selecionando usuários conectados a esses dispositivos. Selecione **Adicionar** na seção **Usuários do** dispositivo.

2. Selecione um ou mais usuários para os quais você deseja monitorar o estado de saúde do dispositivo

   ![adicionar usuário na regra de status de saúde do dispositivo.](../media/select-device-users.png )

   A lista selecionada de usuários mostra na **seção Usuários do** dispositivo. Você pode modificar essa lista adicionando ou removendo usuários.

Todos os dispositivos de entrada usados pela lista de usuários selecionados serão monitorados para o estado de saúde offline.

## <a name="notifications-in-teams-client"></a>Notificações no Teams cliente

As notificações são entregues no canal **MonitoringAlerts** criado automaticamente da Equipe **de Alertas** e Notificações do Administrador.

Uma notificação offline do dispositivo pode incluir as seguintes informações:

- O nome do dispositivo que está offline.
- O usuário do dispositivo offline.
- A que horas o dispositivo ficou offline. (Atualmente, o tempo é apresentado em UTC.)
- O tipo de regra que gerou o alerta.
- Por que um alerta é gerado.