---
title: Painel de Controle - Visão Geral
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Este artigo fornece uma visão geral do novo Painel de Controle.
ms.openlocfilehash: 77e26b810bfd61effa5d94ec3648c440476a7cbe
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824639"
---
# <a name="control-panel"></a>Painel de Controle

O Painel de Controle atual é uma nova versão do Painel de Controle herdado, com o qual ele existe em tandem. O novo Painel de Controle entrou em vigor a partir da Atualização Cumulativa de julho de 2019. Ele ajuda a gerenciar a configuração de servidores, usuários, clientes e dispositivos no ambiente de uma organização.

O Painel de Controle herdado pode não funcionar como a tecnologia Silverlight atingiu o estágio "fim do suporte" em 12 de outubro de 2021. Para obter mais informações, [consulte Silverlight End of Support](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788).

> [!NOTE]
> Para obter informações sobre o Painel de Controle herdado, consulte [Painel](../SfbServer/management-tools/install-and-open-administrative-tools.md)de Controle e navegue até a seção Skype for Business Server **Painel de Controle**.

## <a name="access-control-panel"></a>Painel de Controle de Acesso

Para iniciar o novo Painel de Controle no navegador, insira https:// &lt; pool-FQDN &gt; /macp ou uma URL simples configurada.

O novo Painel de Controle inclui itens de menu comumente usados que abrangem a maioria das necessidades da organização. Há alguns itens de menu do Painel de Controle herdado que não estão disponíveis no novo Painel de Controle. No entanto, há uma opção para o usuário aproveitar as funcionalidades nesses itens de menu por meio de cmdlets do PowerShell. Para obter mais informações, consulte a tabela abaixo.

> [!NOTE]
> A documentação de outros itens de menus será disponibilizada posteriormente de forma em fases.

## <a name="client"></a>Client

|Sub-menu  |Fonte de informações para cmdlet  |
|---------|---------|
|Política da Versão de Cliente         |    [Política de versão do cliente](use-powershell-client-menu.md#client-version-policy)     |
|Configuração da Versão de Cliente      |  [Configuração de Versão de Cliente](use-powershell-client-menu.md#client-version-configuration)       |
|Atualização de Dispositivo    | [Atualização de Dispositivos](use-powershell-client-menu.md#device-update)        |
|Dispositivo de Teste     | [Dispositivo de Teste](use-powershell-client-menu.md#test-device)        |
|Configuração do Log de Dispositivos         |    [Configuração do Log de Dispositivos](use-powershell-client-menu.md#device-log-configuration)     |
|Configuração do dispositivo         |    [Configuração do dispositivo](use-powershell-client-menu.md#device-configuration)     |
|Política de Mobilidade         |    [Política de Mobilidade](use-powershell-client-menu.md#mobility-policy)     |
|Configuração de Notificação por Push         |    [Configuração de Notificação por Push](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Segurança

|Sub-menu  |Fonte de informações para cmdlet  |
|---------|---------|
|Registrador         |    [Registrador](use-powershell-security-menu.md#registrar)     |
|Serviço Web      |  [Serviço Web](use-powershell-security-menu.md#web-service)       |
|Política de PIN    | [Política de PIN](use-powershell-security-menu.md#pin-policy)        |
