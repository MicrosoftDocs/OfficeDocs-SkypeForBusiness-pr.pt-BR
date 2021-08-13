---
title: Configuração do Dispositivo Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Na página Nova Configuração de Dispositivo ou Editar Configuração de Dispositivo, você pode criar ou modificar uma coleção de configurações usadas para gerenciar o Skype for Business Telefone Edition. Essas configurações permitem que você configure coisas como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
ms.openlocfilehash: f19a3d6018252fd0abc1ca717b50230aa5f063516e018e2b5b1745fa06a60388
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316327"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuração de Dispositivo: Criar Nova ou Editar Existente
 
Na página **Nova Configuração de Dispositivo** ou **Editar** Configuração de Dispositivo, você pode criar ou modificar uma coleção de configurações usadas para gerenciar o Skype for Business Telefone Edition. Essas configurações permitem que você configure coisas como o modo de segurança necessário, o nível de log do dispositivo, as configurações de QoS (Qualidade de voz do serviço) e se os telefones devem ser bloqueados automaticamente após um período especificado de inatividade.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Nova Configuração de Dispositivo** ou **Editar Configuração de Dispositivo**:
  
- Adicionar uma nova configuração de dispositivo.
    
- Modificar as propriedades de uma configuração de dispositivo existente.
    
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.
  
- **Escopo** Identifica o escopo (Global ou Site) da configuração do dispositivo.
    
- **Nome** Você pode adicionar ou modificar o nome da configuração do dispositivo.
    
- **Segurança SIP** Você pode configurar requisitos de transporte e autenticação para dispositivos Skype for Business Telefone Edition. É possível selecionar dentre as seguintes opções:
    
  - **Baixo** Permitir qualquer tipo de autorização ou transporte.
    
  - **Médio** NTLM ou Kerberos é necessário para autenticação do usuário.
    
  - **Alto** NTLM ou Kerberos é necessário para autenticação do usuário e O TLS é necessário para conexões SIP.
    
- **Nível de registro em log** Você pode habilitar o registro em log no dispositivo UC. Os valores válidos são: Desativado; Baixo; Médio; e Alto. O valor padrão é Desativado.
    
- **Qualidade de Voz do Serviço (QoS)** Você pode especificar o valor DSCP atribuído ao tráfego de voz emanando de um dispositivo Skype for Business Telefone Edition. O padrão é 40. No entanto, 40 não é o valor normalmente usado para tráfego de áudio; em vez disso, o tráfego de áudio é quase sempre marcado com o código DSCP 46. Para manter a consistência em toda sua rede, convém alterar esse valor para 46.
    
- **Telefone bloqueio** Você pode especificar se os telefones UC se bloquearão automaticamente após um período especificado de inatividade. Veja a seguir as configurações possíveis:
    
  - **Impor o bloqueio de dispositivos** Você pode impor o bloqueio de dispositivo selecionando essa caixa de seleção.
    
  - **Comprimento mínimo do PIN** Você pode especificar o tamanho mínimo do PIN (número de identificação pessoal) usado para desbloquear o telefone. O intervalo do tamanho do PIN é 4 a 15 dígitos. O tamanho padrão é 6 dígitos..
    
  - **Telefone tempo de bloqueio** Você pode especificar o período mínimo de tempo antes de o telefone se fechar. O intervalo do tempo limite é 0 a 60 minutos; o valor padrão é 10 minutos. Insira o valor no formato HH:MM:SS.
    
## <a name="see-also"></a>Confira também

[Configuração do dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)