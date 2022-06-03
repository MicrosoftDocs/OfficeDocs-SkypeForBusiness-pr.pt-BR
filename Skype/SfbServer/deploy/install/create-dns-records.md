---
title: Criar registros DNS para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Resumo: saiba como configurar o DNS e criar registros DNS para uma instalação do Skype for Business Server.'
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860532"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Criar registros DNS para Skype for Business Server
 
**Resumo:** Saiba como configurar o DNS e criar registros DNS para uma instalação do Skype for Business Server.
  
Para Skype for Business Server funcionar corretamente, várias configurações do DNS (Sistema de Nomes de Domínio) devem estar em vigor. Isso é para que os clientes saibam como acessar os serviços e que os servidores saibam uns sobre os outros. Essas configurações precisam ser concluídas apenas uma vez por implantação porque, depois de atribuir uma entrada DNS, ela estará disponível em todo o domínio. Você pode executar as etapas de 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. A criação de registros DNS compreende a etapa 5 de 8. Para obter mais informações sobre como planejar o DNS, consulte [Requisitos ambientais para Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) [ou requisitos de servidor para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> É importante observar que esse é apenas um exemplo de como criar registros DNS em um ambiente DNS Windows Server. Há muitas outras entradas DNS que são necessárias para o Skype for Business Server e o procedimento para criar registros DNS depende do sistema que você está usando para gerenciar o DNS em sua organização. Para obter uma lista completa de requisitos para DNS, consulte [os requisitos de DNS para Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagrama de visão geral.](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurar DNS

Os registros DNS são necessários para que Skype for Business Server funcionem corretamente e possam ser acessados pelos usuários.
  
Este exemplo está usando um FQDN com balanceamento de carga DNS chamado pool.contoso.local. Esse pool consiste em três servidores que executam Skype for Business Server Edição Enterprise. Um Edição Standard servidor front-end pode conter apenas um único servidor. Usando o Edição Standard, você usaria apenas o FQDN (nome de domínio totalmente qualificado) do único servidor Edição Standard ao referenciar a função de front-end em vez de criar um pool de servidores com balanceamento de carga DNS, como mostra este exemplo. Este exemplo simples que usa apenas a função de front-end inclui as entradas DNS na tabela a seguir. Para planejar seus requisitos de DNS específicos, consulte [os requisitos de DNS para Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Descrição**|**Tipo de registro**|**Nome**|**Resolvido como**|**Tipo de balanceamento de carga**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN dos Serviços Web Internos  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP do servidor SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Endereço IP do servidor SFB01  <br/> |DNS  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP do servidor SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Endereço IP do servidor SFB02  <br/> |DNS  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP do servidor SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Endereço IP do servidor SFB03  <br/> |DNS  <br/> |
|Skype for Business Descoberta Automática  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|URL Simples de Reunião  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|URL Simples de Discagem  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|URL Simples do Agendador da Web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|URL Simples de Administração  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware com suporte  <br/> |
|Descoberta herdada  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN do pool (porta 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Criar registros DNS

1. Faça logon no servidor DNS e abra **Gerenciador do Servidor**.
    
2. Clique no menu **suspenso** Ferramentas e clique em **DNS**.
    
3. Na árvore de console do domínio SIP, expanda **Zonas** de Pesquisa Direta e expanda o domínio SIP no qual Skype for Business Server será instalado.
    
4. Clique com o botão direito do mouse no domínio SIP e selecione **Novo Host (A ou AAAA),** conforme mostrado na figura.
    
     ![selecionando o novo registro A.](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Na caixa **Nome** , digite o nome do registro de host (o nome de domínio será acrescentado automaticamente).
    
6. Na caixa Endereço **IP**, digite o endereço IP do servidor front-end individual e selecione Criar registro **PTR (** ponteiro associado) ou Permitir que qualquer usuário autenticado atualize registros **DNS** com o mesmo nome de proprietário, se aplicável. Observe que isso pressupõe que o DNS seja usado para balancear a carga de todo o tráfego, com exceção dos serviços Web. Neste exemplo, temos três servidores front-end, conforme mostrado na tabela.
    
   |**Nome do Servidor**|**Tipo**|**Dados**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Em seguida, crie as entradas de balanceamento de carga DNS para o pool. O balanceamento de carga DNS permite que o DNS envie solicitações para os servidores individuais no pool usando o mesmo nome do pool de DNS. Para obter mais informações sobre DNS e balanceamento de carga, consulte [os requisitos de DNS para Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > O pool de vários servidores está disponível apenas em Edição Enterprise implantações. Se você estiver implantando um único servidor Enterprise server ou Edição Standard, precisará criar apenas um registro A para o servidor único. 
  
    Por exemplo, se você tivesse um pool chamado pool.contoso.local e três servidores front-end, criaria as seguintes entradas DNS:
    
   |**FQDN**|**Tipo**|**Dados**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Continue criando registros A para todos os servidores na implantação planejada. 
    
9. Para criar o registro de serviço (SRV) para descoberta herdada, clique com o botão direito do mouse no domínio SIP e selecione **Outros Novos Registros**.
    
10. Em **Selecione um tipo de registro de recurso**, clique em **Local do Serviço (SRV)** e, em seguida, clique em **Criar Registro**.
    
11. Clique em **Serviço** e digite **_sipinternaltls**.
    
12. Clique em **Protocolo** e digite **_tcp**.
    
13. Clique em **Número da Porta** e digite **5061**.
    
14. Clique **em Host oferecendo esse** serviço e digite o FQDN do pool ou Edição Standard servidor.
    
     ![Captura de tela da caixa de diálogo novo registro de recurso.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Clique em **OK** e em **Concluído**.
    
### <a name="verify-dns-records"></a>Verificar registros DNS

1. Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.
    
2. Clique **em** Iniciar, digite **cmd** e pressione Enter.
    
3. Digite **nslookup \<FQDN of the Front End pool\>** ou **\<FQDN of the Standard Edition server or single Enterprise Edition server\>**, e pressione Enter.
    
4. Continue a verificar o restante dos registros A para sua implantação.
    
5. Se você estiver dando suporte a clientes herdados e tiver criado o registro SRV, verifique-o digitando **set type=srv** no prompt **nslookup** e pressione Enter.
    
6. Digite **_sipinternaltls._tcp. *Domínio*** (por exemplo, _sipinternaltls._tcp.contoso.local) e pressione Enter.
    
7. A saída esperada deve ser semelhante à mostrada na figura. Observe que nem todos os registros DNS são mostrados na saída de exemplo, mas todos os registros devem ser verificados. 
    
     ![Verifique as configurações de DNS.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

