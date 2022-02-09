---
title: Definir um gateway no Construtor de Topologias Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: saiba como definir um gateway PSTN no Construtor de Topologias Skype for Business Server.'
ms.openlocfilehash: 3af081134557e149416ecd8d31b13c64051a1ad4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399915"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definir um gateway no Construtor de Topologias Skype for Business Server
 
**Resumo:** Saiba como definir um gateway PSTN no Construtor de Topologias Skype for Business Server.
  
Siga estas etapas para usar o Construtor de Topologias para definir um par com o qual você pode associar um Servidor de Mediação para fornecer conectividade à PSTN (rede telefônica pública comutado) para usuários habilitados para Enterprise Voice. Um ponto para o Servidor de Mediação pode ser um gateway PSTN, um IP-PBX ou um Controlador de Borda de Sessão (SBC) para um Provedor de Serviços de Telefonia da Internet (ITSP) ao qual você se conecta configurando um tronco SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir um par para o Servidor de Mediação

1. Iniciar Construtor de Topologias: clique em **Iniciar, em** Todos os **Programas, Skype for Business Server** **2015** e clique em Skype for Business Server **Construtor de 2015Topology**.
    
2. Em Skype for Business Server, seu nome de site, Componentes Compartilhados, clique com o botão direito do mouse no nó **Gateways PSTN** e clique em **Novo Gateway PSTN**.
3. Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.
    
    > [!NOTE]
    > Se você especificar o TLS (Transport Layer Security) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do Servidor de Mediação. 
  
4. Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.

5. Defina um tronco raiz par ao gateway PSTN. Um tronco é uma conexão lógica entre um Servidor de Mediação e um gateway identificado exclusivamente pela tupla.
    
    {FQDN do Servidor de Mediação, porta de escuta do Servidor de Mediação (TLS ou TCP) : IP do gateway e FQDN, porta de escuta de gateway}
    
     - Ao definir um gateway PSTN no Construtor de Topologias, você deve definir um tronco raiz para adicionar com êxito o gateway PSTN à sua topologia.
    
     - A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.
    
6. Em Porta de Escuta para **Gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do Servidor de Mediação que serão associadas ao tronco raiz do gateway PSTN. (Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC. Em um Aparelho de Filial Suportável em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)
    
7. Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.
    
    > [!NOTE]
    > Por motivos de segurança, é recomendável implantar um par no Servidor de Mediação que possa usar o TLS. 
  
8. Em **Servidor de Mediação Associado**, selecione o pool do Servidor de Mediação para associar ao tronco raiz deste Gateway PSTN.
    
9. Em **Porta do Servidor de Mediação Associado**, digite a porta de escuta que o Servidor de Mediação usará para mensagens SIP do gateway.
    
    > [!NOTE]
    > Com o suporte a vários troncos Skype for Business Server, você pode definir várias portas de sinalização SIP no Servidor de Mediação para comunicação com vários gateways PSTN. Ao definir um tronco, a porta  do Servidor de Mediação Associada deve estar dentro do intervalo das portas de escuta do respectivo protocolo permitido pelo Servidor de Mediação. Esse intervalo de portas é definido em pools de Skype for Business Server e mediação. Clique com o botão direito do mouse no pool de interesse do Servidor de Mediação e selecione **Editar Propriedades**. Especifique a faixa de porta no campo **Portas de ouvinte**.
  
10. Certifique-se de que o par definido está em execução e usando o FQDN ou o endereço IP especificado. Clique em **Concluir**.
    
11. Clique com o botão direito do **mouse no nó Skype for Business Server** e clique **em Publicar Topologia**.
    

