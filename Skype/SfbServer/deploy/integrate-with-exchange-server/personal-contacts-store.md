---
title: Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: Configure o repositório de contatos pessoal usado pelo Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a>Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server 2015
 
**Resumo:** Configure o armazenamento de contato pessoal usado pelo Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server 2015.
  
Se você estiver integrando Skype para Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, você deverá configurar o armazenamento de contato pessoal em todos os computadores cliente com Skype para negócios. Em particular, você deve configurar Skype para a usar o Exchange como o armazenamento de contato pessoal e, ao mesmo tempo, certifique-se de que os usuários não sejam capazes de substituir essa decisão de negócios. Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.
  
Observe que isso não é necessário em computadores que executam o Skype para negócios.
  
Para configurar esse valor em um único computador, execute os seguinte procedimento:
  
1. No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.
    
2. Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.
    
3. No Editor de Registro, expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Policies**, expanda **Microsoft** e expanda **Communicator**.
    
4. Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.
    
5. Depois que o novo valor é criado, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.
    
6. Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.
    
Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo. Para obter detalhes, consulte a documentação de diretiva de grupo em [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

