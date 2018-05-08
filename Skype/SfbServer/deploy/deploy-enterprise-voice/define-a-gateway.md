---
title: Definir um gateway no Construtor de Topologia no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: Saiba como definir um gateway PSTN no construtor de topologia no Skype para Business Server 2015.'
ms.openlocfilehash: ae8656d60d819a92a22db6e97f83ea847ee15765
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a>Definir um gateway no Construtor de Topologia no Skype for Business Server 2015
 
**Resumo:** Saiba como definir um gateway PSTN no construtor de topologia no Skype para Business Server 2015.
  
Siga estas etapas para usar o construtor de topologias para definir um ponto com os quais você pode associar um servidor de mediação para fornecer conectividade com a rede telefônica pública comutada (PSTN) para usuários habilitados para o Enterprise Voice. Um par ao servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda de sessão (SBC) para um Internet telefonia serviço provedor (ITSP) ao qual você se conecta Configurando um tronco SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir um ponto para o Servidor de Mediação

1. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.
    
2. Em Skype para Business Server, o nome do seu site, componentes compartilhados, clique com botão direito no nó **Gateways PSTN** e clique em **Novo Gateway PSTN**.
3. Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.
    
    > [!NOTE]
    > Se você especificar a segurança de camada de transporte (TLS) como o tipo de transporte, você deve especificar o FQDN ao invés do endereço IP do ponto do servidor de mediação. 
  
4. Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.

5. Defina um tronco de raiz para o gateway PSTN. Um tronco é uma conexão lógica entre um servidor de mediação e um gateway exclusivamente identificado pela tupla.
    
    {FQDN do servidor de mediação, porta de escuta do servidor de mediação (TLS ou TCP): gateway IP e FQDN, porta de escuta do gateway}
    
     - Ao definir um gateway PSTN no construtor de topologia, você deve definir um tronco raiz para adicionar com sucesso o gateway PSTN à sua topologia.
    
     - A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.
    
6. Em **Porta de escuta do Gateway IP/PSTN**, digite a porta de escuta do gateway, PBX ou SBC usarão para mensagens SIP do servidor de mediação que será associado ao tronco raiz do gateway PSTN. (Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC. Em um aparelho de filial persistente em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)
    
7. Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.
    
    > [!NOTE]
    > Por motivos de segurança, é altamente recomendável que você implante um par ao servidor de mediação que possa utilizar TLS. 
  
8. Em **Servidor de mediação associado**, selecione o pool de servidor de mediação para associar o tronco raiz deste Gateway PSTN.
    
9. Em **porta do servidor de mediação associado**, digite a porta de escuta do servidor de mediação usará para mensagens SIP do gateway.
    
    > [!NOTE]
    > Com suporte a troncos múltiplos no Skype para Business Server, você pode definir várias portas no servidor de mediação para comunicação com vários gateways PSTN de sinalização do SIP. Ao definir um tronco, a **porta do servidor de mediação associado** deve estar dentro do intervalo das portas de escuta para o protocolo respectivo permitidos pelo servidor de mediação. Esse intervalo de portas é definido em Skype para Business Server e os Pools de mediação. O pool do servidor de mediação de interesse do mouse em e selecione **Editar propriedades**. Especifique a faixa de porta no campo **Portas de ouvinte**.
  
10. Verifique se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou. Depois, clique em **Concluir**.
    
11. Clique com o botão direito no nó **Skype for Business Server** e, em seguida, clique em **Publicar Topologia**.
    

