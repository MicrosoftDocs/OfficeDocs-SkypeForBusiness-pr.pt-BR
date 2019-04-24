---
title: Configurar o armazenamento de contatos pessoais nos computadores de clientes do Lync 2010
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: Configure o repositório de contatos pessoal usado pelos clientes herdados.'
ms.openlocfilehash: 4afb40f57043988768118a0b83c0afe7e9df0028
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216652"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurar o armazenamento de contatos pessoais nos computadores de clientes do Lync 2010
  
Se você estiver integrando Skype para Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, você deverá configurar o armazenamento de contato pessoal usado pelos clientes. Em particular, você deve configurar Skype para a usar o Exchange como o armazenamento de contato pessoal e, ao mesmo tempo, certifique-se de que os usuários não sejam capazes de substituir essa decisão de negócios. Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.
  
> [!NOTE]
> O procedimento a seguir só é necessária para clientes usando o cliente do Lync 2010 ou anterior. O cliente do Lync 2013 e Skype todos os clientes corporativos não terá a opção de substituição das configurações de armazenamento de contato.
  
Para configurar esse valor em um único computador, execute os seguinte procedimento:
  
1. No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.
2. Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.
3. No Editor de Registro, expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Policies**, expanda **Microsoft** e expanda **Communicator**.
4. Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.
5. Depois do novo valor ser criado, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.
6. Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.

Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo. Para obter detalhes sobre como fazer isso no Windows 10, consulte o artigo de [criar um objeto de diretiva de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
