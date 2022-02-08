---
title: Definir troncos adicionais no Construtor de Topologias Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: saiba como definir um tronco adicional entre um Servidor de Mediação e um ponto de gateway no Construtor de Topologias Skype for Business Server.'
ms.openlocfilehash: d490033f8efff1176fe9cca1fc7cbd7582e5e126
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388893"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definir troncos adicionais no Construtor de Topologias Skype for Business Server
 
**Resumo:** Saiba como definir um tronco adicional entre um Servidor de Mediação e um ponto de gateway no Construtor de Topologias Skype for Business Server.
  
Siga estas etapas para definir um tronco adicional ao qual você pode associar um par a um Servidor de Mediação. Um par fornece usuários habilitados para Enterprise Voice com conectividade com a PSTN (Rede Telefônica Pública Comucionada). Um par pode ser um gateway PSTN, um IP-PBX ou um Controlador de Borda de Sessão (SBC) para um Provedor de Serviços de Telefonia da Internet (ITSP).
  
Um tronco é uma conexão lógica entre um Servidor de Mediação e um gateway.
  
> [!NOTE]
> Este tópico supõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um Servidor de Mediação ou pool localizado ou autônomo, conforme descrito em [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) na documentação implantação.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um Servidor de Mediação e um par de gateway

1. Iniciar Construtor de Topologias: clique em **Iniciar, em** Todos os **Programas, Skype for Business Server** **2015** e clique em Skype for Business Server **Construtor de 2015Topology**.
    
2. Em Skype for Business Server, seu nome de site, **Componentes Compartilhados**, clique com o botão direito do mouse no nó Troncos e clique em **Novo Tronco**. 
   1. Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Não é possível ter dois troncos com o mesmo nome.
    
      > [!NOTE]
      > Se você especificar o TLS (Transport Layer Security) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do Servidor de Mediação. 
  
3. Em **Gateway PSTN associado**, selecione o par de gateway PSTN para associar a esse tronco.
    5. Em Porta de Escuta para **gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do Servidor de Mediação que devem ser associadas a esse tronco. As portas par padrão são 5066 para Protocolo de Controle de Transmissão (TCP) e 5067 para TLS (Transport Layer Security). As portas padrão do Aparelho de Filial Suportável são 5081 para TCP e 5082 para TLS.
    
4. Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o par usa.
    
    > [!NOTE]
    > Por motivos de segurança, é recomendável implantar um par no Servidor de Mediação que possa usar o TLS. 
  
5. Em **Servidor de Mediação Associado**, selecione o pool do Servidor de Mediação para associar ao tronco raiz deste par
    
6. Em **Porta do Servidor de Mediação Associado**, digite a porta de escuta que o Servidor de Mediação receberá mensagens SIP do par.
    
    > [!NOTE]
    > Com suporte a vários troncos Skype for Business Server, dois troncos com nomes de tronco diferentes não podem ser configurados com a mesma  porta do Servidor de Mediação Associada e a Porta de Escuta para **gateway IP/PSTN**
  
    > [!NOTE]
    > Com o suporte a vários troncos Skype for Business Server, várias portas de sinalização SIP podem ser definidas no Servidor de Mediação para comunicação com vários pares. Ao definir um tronco, o número  da porta do Servidor de Mediação Associado deve estar dentro do intervalo das portas de escuta do respectivo protocolo permitido pelo Servidor de Mediação. Esse intervalo de portas é definido em pools Skype for Business Server e Servidor de Mediação. Clique com o botão direito do mouse no pool relevante do Servidor de Mediação e selecione **Editar Propriedades**. Especifique a faixa de porta no campo **Portas de ouvinte**.
  
7. Clique em **OK**. 
    

