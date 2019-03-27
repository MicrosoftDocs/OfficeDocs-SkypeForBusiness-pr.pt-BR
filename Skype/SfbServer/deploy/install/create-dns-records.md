---
title: Criar registros DNS para Skype for Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Resumo: Saiba como configurar o DNS e criar registros DNS para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 35e8aecea74cc74cda6ea086a1765642885a091e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890680"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Criar registros DNS para Skype for Business Server
 
**Resumo:** Saiba como configurar o DNS e criar registros DNS para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Para Skype para Business Server funcionem adequadamente, várias configurações de sistema de nome de domínio (DNS) devem ser in-loco. Isso é para que os clientes instruídos como acessar os serviços e que os servidores saber sobre umas às outras. Essas configurações precisam ser concluída apenas uma vez por implantação porque uma vez você atribuir uma entrada DNS, ele está disponível em todo o domínio. Você pode executar os passos 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. Criar registros DNS compreende a etapa 5 de 8. Para obter mais informações sobre o planejamento de DNS, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> É importante notar que este é apenas um exemplo de como criar registros DNS em um ambiente DNS do Windows Server. Há muitas outras entradas DNS necessários para Skype para Business Server e o procedimento para criar registros DNS depende do sistema que você está usando para gerenciar o DNS em sua organização. Para obter uma lista completa dos requisitos de DNS, consulte [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Diagrama de visão geral](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Configurar DNS

Registros DNS são necessários para Skype para Business Server funcionar corretamente e ser acessível pelos usuários.
  
Este exemplo está usando uma carga balanceada FQDN do DNS chamada pool.contoso.local. Este pool consiste em três servidores que executam o Skype para Business Server Enterprise Edition. Um servidor front-end da Standard Edition pode conter apenas um único servidor. No Standard Edition, você usaria o FQDN (nome de domínio totalmente qualificado) do servidor único Standard Edition ao referenciar a função de front-end em vez de criar um pool de carga balanceada DNS de servidores, como mostra este exemplo. Este simples exemplo que usa apenas a função de front-end inclui as entradas DNS na seguinte tabela. Para planejar seus requisitos de DNS específicos, consulte [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Descrição**|**Tipo de registro**|**Nome**|**Resolve para**|**Tipo de balanceamento de carga**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN dos Serviços Web Internos  <br/> |A  <br/> |webint.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP de servidor SFB01  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |Endereço IP de servidor SFB01  <br/> |DNS  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP de servidor SFB02  <br/> |DNS  <br/> |
|FQDN do SFB02  <br/> |A  <br/> |SFB02.contoso.local  <br/> |Endereço IP de servidor SFB02  <br/> |DNS  <br/> |
|FQDN do pool  <br/> |A  <br/> |pool.contoso.local  <br/> |Endereço IP de servidor SFB03  <br/> |DNS  <br/> |
|FQDN do SFB03  <br/> |A  <br/> |SFB03.contoso.local  <br/> |Endereço IP de servidor SFB03  <br/> |DNS  <br/> |
|Descoberta Automática do Skype for Business  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|URL Simples de Reunião  <br/> |A  <br/> |meet.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|URL Simples de Discagem  <br/> |A  <br/> |dialin.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|URL Simples de Agendador da Web  <br/> |A  <br/> |scheduler.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|URL Simples de Administração  <br/> |A  <br/> |admin.contoso.local  <br/> |VIP para Serviços Web Internos  <br/> |Software e hardware suportados  <br/> |
|Descoberta Herdada  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |FQDN do Pool (porta 5061)  <br/> |N/D  <br/> |
   
### <a name="create-dns-records"></a>Criar registros DNS

1. Faça logon no servidor DNS e abra o **Gerenciador de Servidor**.
    
2. Clique no menu suspenso **Ferramentas** e clique em **DNS**.
    
3. Na árvore de console do domínio SIP, expanda **Zonas de pesquisa direta**e, em seguida, expanda o domínio SIP no qual Skype para Business Server será instalado.
    
4. Clique com o botão direito sobre o domínio SIP e selecione **Novo Host (A ou AAAA)**, conforme mostra a figura.
    
     ![selecionando um registro de novo](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Na caixa **Nome**, digite o nome do registro host (o nome do domínio será automaticamente acrescentado).
    
6. Na **caixa de endereço IP**, digite o endereço IP do servidor front-end individual e selecione **Criar registro de ponteiro associado (PTR)** ou **Permitir que qualquer usuário autenticado atualize registros de DNS com o mesmo nome de proprietário**, se aplicável. Observe que essa ação presume que o DNS será usado para balanceamento de carga de todo o tráfego com exceção de serviços Web. Neste exemplo, temos três servidores front-end, conforme mostrado na tabela.
    
   |**Nome do servidor**|**Tipo**|**Dados**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Em seguida, crie as entradas de balanceamento de carga DNS para o pool. O balanceamento de carga DNS permite que o DNS envie solicitações para os servidores individuais no pool enquanto usa o mesmo nome do pool DNS. Para obter mais informações sobre o DNS e balanceamento de carga, consulte [requisitos de DNS para Skype para Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > O agrupamento de vários servidores em pools está disponível apenas em implantações da versão Enterprise Edition. Se você estiver implantando um único servidor Enterprise ou Standard Edition, terá que criar somente um registro A para o único servidor. 
  
    Por exemplo, se o nome de seu pool for pool.contoso.local e você tiver três servidores front-end, você deve criar as seguintes entradas DNS:
    
   |**FQDN**|**Tipo**|**Dados**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Continue criando registros A para todos os servidores na implantação planejada. 
    
9. Para criar o registro de serviços (SRV) para descoberta herdada, clicar com o botão direito do mouse sobre o domínio SIP e selecione **Outros novos registros**.
    
10. Em **Selecionar um tipo de registro de recurso**, clique em **Local do serviço(SRV)**, e depois clique em **Criar registro**.
    
11. Clique em **Serviço** e digite **_sipinternaltls**.
    
12. Clique em **Protocolo**, e depois digite **_tcp**.
    
13. Clique em **Número da porta** e digite **5061**.
    
14. Clique em **Host que oferece este serviço** e digite o FQDN do pool ou o servidor Standard Edition.
    
     ![Captura de tela da caixa de diálogo de registro de recurso novo.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Clique em **OK** e em **Concluído**.
    
### <a name="verify-dns-records"></a>Verificar registros DNS

1. Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.
    
2. Clique em **Iniciar**, digite **cmd** e aperte Enter.
    
3. Tipo **nslookup \<FQDN do pool de Front-End\> ** ou ** \<FQDN do servidor Standard Edition ou único servidor Enterprise Edition\>**, e pressione Enter.
    
4. Continue verificando os demais registros A para sua implantação.
    
5. Se você estiver suportando clientes herdados e tiver criado o registro SRV, verifique-o digitando **set type=srv** no prompt **nslookup** e depois aperte Enter.
    
6. Digite **sipinternaltls. *domínio* ** (por exemplo, _sipinternaltls._tcp.contoso.local), e pressione Enter.
    
7. O resultado esperado deve ser similar ao mostrado na figura. Observe que nem todos os registros DNS são mostrados na amostra do resultado, mas todos os registros devem ser verificados. 
    
     ![Verifique se as configurações de dns.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

