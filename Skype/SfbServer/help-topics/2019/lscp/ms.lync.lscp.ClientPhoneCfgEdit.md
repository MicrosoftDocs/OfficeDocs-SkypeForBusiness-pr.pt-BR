---
title: Configuração de dispositivo criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Na página nova configuração de dispositivo ou Editar configuração de dispositivo, você pode criar ou modificar um conjunto de configurações usadas para gerenciar Skype para negócios Phone Edition. Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
ms.openlocfilehash: 9010ca1850220e0fd35ec01a666adfb0f119f4cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891632"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuração de Dispositivo: Criar Nova ou Editar Existente
 
Na página **Nova configuração de dispositivo** ou **Editar configuração de dispositivo** , você pode criar ou modificar um conjunto de configurações usadas para gerenciar Skype para negócios Phone Edition. Essas configurações permitem que você configure aspectos como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Nova Configuração de Dispositivo** ou  **Editar Configuração de Dispositivo**:
  
- Adicionar uma nova configuração de dispositivo.
    
- Modificar as propriedades de uma configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (Global ou Site) da configuração de dispositivo.
    
- **Nome** É possível adicionar ou modificar o nome da configuração de dispositivo.
    
- **Segurança SIP** Você pode configurar requisitos de transporte e autenticação para Skype para dispositivos de negócios Phone Edition. É possível selecionar dentre as seguintes opções:
    
  - **Baixo** Permitir que qualquer tipo de autorização ou transporte.
    
  - **Médio** NTLM ou Kerberos são obrigatórios para a autenticação de usuário.
    
  - **Alta** NTLM ou Kerberos são obrigatórios para a autenticação de usuário e TLS é necessário para conexões SIP.
    
- **Nível de log** Você pode habilitar o log do dispositivo de comunicação unificada. Os valores válidos são: Desativado; Baixo; Médio; e Alto. O valor padrão é Desativado.
    
- **Qualidade de voz do serviço (QoS)** Você pode especificar o valor DSCP atribuído ao tráfego de voz emanando de um Skype para o dispositivo de negócios Phone Edition. O padrão é 40. No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46. Para manter a consistência em toda sua rede, convém alterar esse valor para 46.
    
- **Bloqueio de telefone** Você pode especificar se ou não telefones UC serão bloqueado automaticamente sozinhos após um período de inatividade especificado. Veja a seguir as configurações possíveis:
    
  - **Impor bloqueio de dispositivo** É possível aplicar o bloqueio do telefone marcando essa caixa de seleção.
    
  - **Tamanho mínimo do PIN** Você pode especificar o comprimento mínimo para o número de identificação pessoal (PIN) que é usado para desbloquear o telefone. O tamanho do PIN é de quatro a 15 dígitos. O tamanho padrão é de seis dígitos.
    
  - **Tempo limite de bloqueio de telefone** Você pode especificar o comprimento mínimo de tempo antes que os bloqueios de telefone em si. O intervalo para o tempo limite é de 0 a 60 minutos; o valor padrão é de 10 minutos. Insira o valor no formato HH:MM:SS.
    
## <a name="see-also"></a>Confira também

[Configuração do dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
