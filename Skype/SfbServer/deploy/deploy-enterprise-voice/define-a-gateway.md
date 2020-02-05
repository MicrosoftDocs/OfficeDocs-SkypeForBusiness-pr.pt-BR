---
title: Definir um gateway no construtor de topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: saiba como definir um gateway PSTN no construtor de topologias no Skype for Business Server.'
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767724"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definir um gateway no construtor de topologias no Skype for Business Server
 
**Resumo:** Saiba como definir um gateway PSTN no construtor de topologias no Skype for Business Server.
  
Siga estas etapas para usar o construtor de topologias para definir um par com o qual você pode associar um servidor de mediação para fornecer conectividade à rede telefônica pública comutada (PSTN) para usuários habilitados para Enterprise Voice. Um peer para o servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda de sessão (SBC) para um provedor de serviços de telefonia pela Internet (ITSP) ao qual você se conecta Configurando um tronco SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir um ponto para o Servidor de Mediação

1. Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.
    
2. Em Skype for Business Server, o nome do seu site, componentes compartilhados, clique com o botão direito do mouse no nó **gateways PSTN** e clique em **novo gateway PSTN**.
3. Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.
    
    > [!NOTE]
    > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação. 
  
4. Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.

5. Defina um tronco raiz para o gateway PSTN. Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla.
    
    {Servidor de mediação do FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}
    
     - Ao definir um gateway PSTN no construtor de topologias, você deve definir um tronco raiz para adicionar com êxito o gateway PSTN à sua topologia.
    
     - A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.
    
6. Em **porta de escuta para gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do servidor de mediação que serão associadas ao tronco raiz do gateway PSTN. (Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC. Em um aparelho de ramificação sobreviventes em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)
    
7. Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.
    
    > [!NOTE]
    > Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS. 
  
8. Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse gateway PSTN.
    
9. Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação usará para mensagens SIP do gateway.
    
    > [!NOTE]
    > Com o suporte a vários troncos no Skype for Business Server, você pode definir várias portas de sinalização SIP no servidor de mediação para comunicação com vários gateways PSTN. Ao definir um tronco, a **porta do servidor de mediação associada** deve estar dentro do intervalo das portas de escuta do respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido no Skype for Business Server e em pools de mediação. Clique com o botão direito do mouse no pool de servidores de mediação de interesse e selecione **Editar propriedades**. Specify the port range in the **Listening ports** field.
  
10. Verifique se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou. Depois, clique em **Concluir**.
    
11. Clique com o botão direito no nó **Skype for Business Server** e, em seguida, clique em **Publicar Topologia**.
    

