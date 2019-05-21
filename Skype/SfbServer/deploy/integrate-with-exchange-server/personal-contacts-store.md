---
title: Configurar o repositório de contatos pessoais em computadores cliente do Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: configurar o repositório de contatos pessoal usado pelos clientes herdados.'
ms.openlocfilehash: ba9cb7ee485f94162a642f8e877213a7bcd47c55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278081"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar o repositório de contatos pessoais em computadores cliente do Lync 2010
  
Se você estiver integrando o Skype for Business Server 2015 e o servidor do Exchange 2016 ou Exchange Server 2013, configure o repositório de contatos pessoal usado pelos clientes. Em particular, você deve configurar o Skype for Business para usar o Exchange como o repositório de contatos pessoais e, ao mesmo tempo, garantir que os usuários não consigam substituir essa decisão. Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.
  
> [!NOTE]
> O procedimento a seguir só é necessário para clientes que usam o cliente Lync 2010 ou anterior. O cliente do Lync 2013 e todos os clientes do Skype for Business não terão a opção de substituir as configurações da loja de contatos.
  
Para configurar esse valor em um único computador, execute os seguinte procedimento:
  
1. No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.
2. Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.
3. No Editor de Registro, expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Policies**, expanda **Microsoft** e expanda **Communicator**.
4. Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.
5. Depois do novo valor ser criado, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.
6. Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.

Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo. Para obter detalhes sobre como fazer isso no Windows 10, consulte o artigo [criar um objeto de política de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
