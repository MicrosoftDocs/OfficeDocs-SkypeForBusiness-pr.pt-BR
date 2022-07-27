---
title: Monitoramento e alertas de dispositivos do Microsoft Teams
author: cazawideh
ms.author: czawideh
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba como usar os recursos de monitoramento e alerta do Teams no Centro de administração do Microsoft Teams para monitorar proativamente o estado de integridade dos dispositivos do Teams
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 81994e3462fe678c40506d6a11b343ba733995cd
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023802"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Monitoramento de integridade de dispositivos do Microsoft Teams

O monitoramento de integridade do dispositivo no Centro de administração do Microsoft Teams oferece a capacidade de monitorar proativamente a integridade de vários dispositivos do Teams. Monitore o estado offline de um dispositivo e receba alertas em tempo real se o dispositivo monitorado em sua organização ficar offline.  

Antes de começar, você precisará das permissões de criação de equipes/canal em seu locatário. [Saiba mais](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurar regra de estado do dispositivo

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, selecione Notificações **& regras de alertas** > .

   ![Seção regras no centro de administração.](../media/select-rules.png)

2. Na página **Regras** , selecione **Regra de estado do dispositivo**.

3. Selecione o dispositivo para configurar a regra de estado para habilitar alertas.

    ![Página de regra de estado de dispositivos do Teams.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretar a configuração da regra


|Campo |Descrição  |
|--------|-------------|
|**Tipo de regra**   |A regra de estado do dispositivo ajuda você a gerenciar com eficiência. Os dispositivos do Teams e são classificados como um tipo de gerenciamento de dispositivo. No futuro, mais regras de tipo de gerenciamento de dispositivo estarão disponíveis para monitorar outros recursos relacionados (exemplos podem incluir: dispositivo não íntegro e o status de entrada do dispositivo).|
|**Condição**   |Você poderá monitorar a integridade dos dispositivos se eles estiverem offline. [Saiba mais sobre](../devices/device-management.md) o gerenciamento de dispositivos no Centro de administração do Teams. |
|**Escopo**   |Você pode especificar com que frequência deseja monitorar o status de integridade do dispositivo mencionando a frequência de avaliação de regra. Por padrão, os dispositivos do Teams serão monitorados quase em tempo real se estiverem offline. |
|**Usuários do dispositivo**   |Você pode especificar quais dispositivos precisam de monitoramento proativo de estátua offline selecionando-os com base em usuários conectados. Consulte Selecionar [dispositivos para obter mais](#select-devices-for-configuration) detalhes. |
|**Ações** >  **Alerta de canal**   |Na seção Ações, você pode especificar os canais das equipes para os quais deseja obter alertas. Atualmente, uma equipe padrão chamada **Administração Alertas** e Notificações e um canal chamado **MonitoringAlerts** será criado no qual as notificações serão entregues. <BR/> <BR/> Administradores globais e administradores do Teams em seu locatário serão adicionados automaticamente a essa equipe padrão.|
|**Ações** >  **Webhook**   |Você também pode obter notificações com um webhook externo (opcional). Especifique uma URL de webhook público externa na seção webhook em que uma carga de notificação JSON será enviada. <BR/> <BR/>  A carga de notificação, por meio de webhooks, pode ser integrada a outros sistemas em sua organização para criar fluxos de trabalho personalizados.<br/><br/> 

**Esquema de carga JSON para webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string"} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Carga JSON de exemplo**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Selecionar dispositivos para configuração

1. Você pode selecionar os dispositivos do Teams que deseja monitorar selecionando usuários conectados a esses dispositivos. Selecione **Adicionar** na **seção Usuários do** dispositivo.

2. Selecione um ou mais usuários para os quais você deseja monitorar o estado de integridade do dispositivo

   ![adicionar usuário na regra de status de integridade do dispositivo.](../media/select-device-users.png )

   A lista selecionada de usuários é exibida na **seção Usuários do** dispositivo. Você pode modificar essa lista adicionando ou removendo usuários.

Todos os dispositivos de entrada usados pela lista selecionada de usuários serão monitorados para o estado de integridade offline.

## <a name="notifications-in-teams-client"></a>Notificações no cliente do Teams

As notificações são entregues no canal **MonitoringAlerts** criado automaticamente da equipe **Administração alertas e notificações**. Você receberá um alerta dentro de 15 minutos após o dispositivo ficar offline. 

Uma notificação offline do dispositivo pode incluir as seguintes informações:

- O nome do dispositivo que está offline.
- O usuário do dispositivo offline.
- A que horas o dispositivo ficou offline. (Atualmente, a hora é apresentada em UTC.)
- O tipo de regra que gerou o alerta.
- Por que um alerta é gerado.
