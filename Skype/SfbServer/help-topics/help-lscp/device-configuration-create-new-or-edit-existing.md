---
title: Configuração do dispositivo criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Na página configuração do novo dispositivo ou editar configuração do dispositivo, você pode criar ou modificar um conjunto de configurações usadas para gerenciar o Skype for Business Phone Edition. Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
ms.openlocfilehash: 0bd8d79a97f9dd48faff09f1d7a8e0cfb41473f6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700316"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuração de Dispositivo: Criar Nova ou Editar Existente
 
Na página **configuração do novo dispositivo** ou **Editar configuração do dispositivo** , você pode criar ou modificar um conjunto de configurações usadas para gerenciar o Skype for Business Phone Edition. Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Nova Configuração de Dispositivo** ou  **Editar Configuração de Dispositivo**:
  
- Adicionar uma nova configuração de dispositivo.
    
- Modificar as propriedades de uma configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (global ou site) da configuração do dispositivo.
    
- **Nome** Você pode adicionar ou modificar o nome da configuração do dispositivo.
    
- **Segurança SIP** Você pode configurar requisitos de transporte e autenticação para dispositivos do Skype for Business Phone Edition. É possível selecionar dentre as seguintes opções:
    
  - **Baixo** Permitir qualquer tipo de autorização ou transporte.
    
  - **Média** NTLM ou Kerberos é necessário para autenticação do usuário.
    
  - **Alta** NTLM ou Kerberos é necessário para a autenticação do usuário e o TLS é necessário para conexões SIP.
    
- **Nível de log** Você pode habilitar o registro em log no dispositivo de comunicação unificada. Os valores válidos são: Desativado; Baixo; Médio; e Alto. O valor padrão é Desativado.
    
- **Qualidade de serviço (QoS) de voz** Você pode especificar o valor de DSCP atribuído a um tráfego de voz que emana de um dispositivo Skype for Business Phone Edition. O padrão é 40. No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46. Para manter a consistência em toda sua rede, convém alterar esse valor para 46.
    
- **Bloqueio de telefone** Você pode especificar se os telefones UC serão bloqueados automaticamente após um período de inatividade especificado. Veja a seguir as configurações possíveis:
    
  - **Impor o bloqueio de dispositivo** Você pode impor o bloqueio do dispositivo marcando essa caixa de seleção.
    
  - **Comprimento mínimo do PIN** Você pode especificar o comprimento mínimo para o número de identificação pessoal (PIN) que é usado para desbloquear o telefone. O tamanho do PIN é de quatro a 15 dígitos. O tamanho padrão é de seis dígitos.
    
  - **Tempo limite de bloqueio de telefone** Você pode especificar o período mínimo de tempo até que o telefone seja bloqueado. O intervalo para o tempo limite é de 0 a 60 minutos; o valor padrão é de 10 minutos. Insira o valor no formato HH:MM:SS.
    
## <a name="see-also"></a>Confira também

[Configuração do dispositivo](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
