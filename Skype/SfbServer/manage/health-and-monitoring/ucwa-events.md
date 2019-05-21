---
title: Eventos do UCWA no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumo: Saiba mais sobre a API da Web de comunicação unificada (UCWA) no Skype for Business Server.'
ms.openlocfilehash: bbded70318190fb4fa68ab524a696183c97ff07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279694"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos do UCWA no Skype for Business Server
 
**Resumo:** Saiba mais sobre a API da Web de comunicação unificada (UCWA) no Skype for Business Server.
  
O Skype for Business Server usa a API da Web de comunicação unificada (UCWA) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.
  
A UCWA gravará registros de comportamento operacional como tipos de evento Informacional, Aviso e Erro. A tabela a seguir descreve tais eventos que podem ser gravados com componentes da UCWA.
  
|**ID do evento**|**Tipo de evento**|**Resumo**|**Causa e resolução**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Erro  <br/> |A UCWA encontrou uma exceção inesperada durante a inicialização  <br/> |Ocorreu um erro inesperado durante a inicialização  <br/> Examine os detalhes da exceção na entrada de log do evento associado para determinar a possível causa  <br/> |
|20003  <br/> |Erro  <br/> |A UCWA encontrou uma exceção não manipulada  <br/> |Ocorreu uma exceção não manipulada  <br/> Reinicie o servidor. Se o problema persistir, entre em contato com o suporte do produto  <br/> |
|20004  <br/> |Erro  <br/> |Não é possível acessar o Exchange para foto HD  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperação de uma falha ao acessar o Exchange para foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Erro  <br/> |Não é possível acessar o Exchange para pesquisa de contato  <br/> |A conexão com o Exchange não está disponível  <br/> Certifique-se de que a conexão com o Exchange está disponível  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperação de uma falha em pesquisar contato no Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Aviso  <br/> |Tente assinar mais de uma assinatura de presença permitida por aplicativo  <br/> |Tente assinar mais de uma assinatura de presença permitida por aplicativo  <br/> Verifique se os clientes possuem assinaturas desnecessárias  <br/> |
|20009  <br/> |Aviso  <br/> |Tente assinar mais de uma assinatura de presença permitida por lote  <br/> |Tente assinar mais de uma assinatura de presença permitida por lote  <br/> Verifique se os clientes possuem assinaturas desnecessárias  <br/> |
|20010  <br/> |Erro  <br/> |Não é possível recuperar os dados inband  <br/> |Não é possível recuperar os dados inband  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20011  <br/> |Erro  <br/> |Não é possível assinar a presença  <br/> |Não é possível assinar a presença  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20012  <br/> |Erro  <br/> |Falha ao registrar o ponto de extremidade  <br/> |Falha ao registrar o ponto de extremidade  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
|20013  <br/> |Erro  <br/> |A MCU de IM não está disponível  <br/> |A MCU de IM não está disponível  <br/> Consulte se a MCU de IM está sendo executada  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de IM  <br/> |N/D  <br/> |
|20015  <br/> |Erro  <br/> |A MCU de AV não está disponível  <br/> |A MCU de AV não está disponível  <br/> Consulte se a MCU de AV está sendo executada  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de AV  <br/> |N/D  <br/> |
|20017  <br/> |Erro  <br/> |A MCU de AS não está disponível  <br/> |A MCU de AS não está disponível  <br/> Consulte se a MCU de AS está sendo executada  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de AS  <br/> |N/D  <br/> |
|20019  <br/> |Erro  <br/> |A MCU de Dados não está disponível  <br/> |A MCU de Dados não está disponível  <br/> Consulte se a MCU de Dados está sendo executada  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperação de uma falha ao conectar ao MCU de dados  <br/> |N/D  <br/> |
|20021  <br/> |Erro  <br/> |Não é possível participar da MCU de IM  <br/> |Não é possível participar da MCU de IM  <br/> Consulte se a MCU de IM está sendo executada  <br/> |
|20022  <br/> |Erro  <br/> |Não é possível participar da MCU de AV  <br/> |Não é possível participar da MCU de AV  <br/> Consulte se a MCU de AV está sendo executada  <br/> |
|20023  <br/> |Erro  <br/> |Não é possível participar da MCU de AS  <br/> |Não é possível participar da MCU de AS  <br/> Consulte se a MCU de AS está sendo executada  <br/> |
|20024  <br/> |Erro  <br/> |Não é possível participar da MCU de Dados  <br/> |Não é possível participar da MCU de Dados  <br/> Consulte se a MCU de Dados está sendo executada  <br/> |
|20025  <br/> |Erro  <br/> |Não é possível acessar o diretório ativo para foto  <br/> |A conexão com o diretório ativo não está disponível  <br/> Certifique-se de que a conexão com o diretório ativo está disponível  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperação de falha ao acessar o diretório ativo para foto  <br/> |N/D  <br/> |
|20027  <br/> |Aviso  <br/> |Não é possível desserializar  <br/> |Não é possível desserializar  <br/> Se o problema persistir entre em contato com o suporte do produto  <br/> |
   

