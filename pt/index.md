---
layout: publicar
title: Web Vitals
description: Métricas essenciais para um site saudável
hero: image / admin / BHaoqqR73jDWe6FL2kfw.png
authors:
  - philipwalton
date: 30-04-2020
updated: 21-07-2020
tags:
  - Métricas
  - atuação
  - web-vitals
---

A otimização da qualidade da experiência do usuário é a chave para o sucesso a longo prazo de qualquer site na web. Quer você seja proprietário de uma empresa, comerciante ou desenvolvedor, o Web Vitals pode ajudá-lo a quantificar a experiência do seu site e identificar oportunidades de melhoria.

## Visão geral

Web Vitals é uma iniciativa do Google para fornecer orientação unificada para sinais de qualidade essenciais para proporcionar uma ótima experiência ao usuário na web.

O Google forneceu várias ferramentas ao longo dos anos para medir e relatar o desempenho. Alguns desenvolvedores são especialistas no uso dessas ferramentas, enquanto outros consideram difícil acompanhar a abundância de ferramentas e métricas.

Os proprietários de sites não devem ser gurus de desempenho para compreender a qualidade da experiência que estão proporcionando aos usuários. A iniciativa Web Vitals visa simplificar o cenário e ajudar os sites a se concentrarem nas métricas que mais importam, o **Core Web Vitals** .

## Core Web Vitals

Core Web Vitals são o subconjunto de Web Vitals que se aplicam a todas as páginas da web, devem ser medidos por todos os proprietários de sites e serão exibidos em todas as ferramentas do Google. Cada um dos vitais essenciais da Web representa uma faceta distinta da experiência do usuário, é mensurável [no campo](/user-centric-performance-metrics/#how-metrics-are-measured) e reflete a experiência do mundo real de um resultado crítico [centrado no usuário](/user-centric-performance-metrics/#how-metrics-are-measured) .

As métricas que constituem o Core Web Vitals irão [evoluir](#evolving-web-vitals) com o tempo. O conjunto atual para 2020 se concentra em três aspectos da experiência do usuário - *carregamento* , *interatividade* e *estabilidade visual* - e inclui as seguintes métricas (e seus respectivos limites):

<div class="w-stack w-stack--center w-stack--md">
<img src="lcp_ux.svg" width="400px" height="350px" alt="Recomendações de limite de pintura com maior conteúdo"><img src="fid_ux.svg" width="400px" height="350px" alt="Primeiras recomendações de limite de atraso de entrada"><img src="cls_ux.svg" width="400px" height="350px" alt="Recomendações de limite de mudança de layout cumulativo">
</div>

- **[Largest Contentful Paint (LCP)](/lcp/)** : mede o desempenho de *carregamento.* Para fornecer uma boa experiência ao usuário, o LCP deve ocorrer dentro de **2,5 segundos** após o início do carregamento da página.
- **[Atraso na primeira entrada (FID)](/fid/)** : mede a *interatividade* . Para fornecer uma boa experiência do usuário, as páginas devem ter um FID de menos de **100 milissegundos** .
- **[Mudança cumulativa de layout (CLS)](/cls/)** : mede *a estabilidade visual* . Para fornecer uma boa experiência do usuário, as páginas devem manter um CLS inferior a **0,1.**

Para cada uma das métricas acima, para garantir que você está atingindo a meta recomendada para a maioria dos seus usuários, um bom limite para medir é o **75º percentil** de carregamentos de página, segmentado em dispositivos móveis e desktop.

As ferramentas que avaliam a conformidade do Core Web Vitals devem considerar a passagem de uma página se atender às metas recomendadas no 75º percentil para todas as três métricas acima.

{% Aside%} Para saber mais sobre a pesquisa e a metodologia por trás dessas recomendações, consulte: [Definindo os limites das métricas](/defining-core-web-vitals-thresholds/) essenciais da Web vitals {% endAside%}

### Ferramentas para medir e relatar Core Web Vitals

O Google acredita que o Core Web Vitals é essencial para todas as experiências na web. Como resultado, está empenhada em trazer à tona essas métricas [em todas as suas ferramentas populares](/vitals-tools/) . As seções a seguir detalham quais ferramentas suportam o Core Web Vitals.

#### Ferramentas de campo para medir os vitais essenciais da Web

O[Relatório de experiência do usuário do Chrome](https://developers.google.com/web/tools/chrome-user-experience-report) coleta dados anônimos e reais de medição do usuário para cada Core Web Vital. Esses dados permitem que os proprietários de sites avaliem rapidamente seu desempenho sem a necessidade de instrumentar manualmente as análises em suas páginas e fornece ferramentas como o [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) e o [relatório Core Web Vitals do](https://support.google.com/webmasters/answer/9205520) Search Console.

<div class="w-table-wrapper">
  <table>
    <tr>
      <td> </td>
      <td>LCP</td>
      <td>FID</td>
      <td>CLS</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/web/tools/chrome-user-experience-report">Relatório de experiência do usuário do Chrome</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/speed/pagespeed/insights/">PageSpeed Insights</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://support.google.com/webmasters/answer/9205520">Search Console (relatório Core Web Vitals)</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
  </table>
</div>

{% Aside%} Para obter orientação sobre como usar essas ferramentas e qual ferramenta é a certa para o seu caso de uso, consulte: [Primeiros passos com a medição dos](/vitals-measurement-getting-started/) vitais da Web {% endAside%}

Os dados fornecidos pelo Relatório de experiência do usuário do Chrome oferecem uma maneira rápida de avaliar o desempenho dos sites, mas não fornece a telemetria de visualização por página detalhada, que muitas vezes é necessária para diagnosticar, monitorar e reagir rapidamente a regressões com precisão. Como resultado, é altamente recomendável que os sites configurem seu próprio monitoramento de usuário real.

#### Meça os vitais essenciais da web em JavaScript

Cada um dos vitais essenciais da Web pode ser medido em JavaScript usando APIs da web padrão.

A maneira mais fácil de medir todos os [vitais essenciais da Web é usar a biblioteca JavaScript web-vitals](https://github.com/GoogleChrome/web-vitals) , um pequeno invólucro pronto para produção em torno das APIs da web subjacentes que mede cada métrica de uma forma que corresponda com precisão à forma como são relatadas por todos os Ferramentas do Google listadas acima.

Com a [biblioteca web-vitals](https://github.com/GoogleChrome/web-vitals) , medir cada métrica é tão simples quanto chamar uma única função (consulte a documentação para detalhes completos de [uso](https://github.com/GoogleChrome/web-vitals#usage) e [API](https://github.com/GoogleChrome/web-vitals#api) ):

```js
import {getCLS, getFID, getLCP} from 'web-vitals';

function sendToAnalytics(metric) {
  const body = JSON.stringify(metric);
  // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
  (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
      fetch('/analytics', {body, method: 'POST', keepalive: true});
}

getCLS(sendToAnalytics);
getFID(sendToAnalytics);
getLCP(sendToAnalytics);
```

Depois de configurar seu site para usar a [biblioteca web-vitals](https://github.com/GoogleChrome/web-vitals) para medir e enviar seus dados Core Web Vitals para um endpoint analítico, a próxima etapa é agregar e relatar esses dados para ver se suas páginas estão atingindo os limites recomendados para pelo menos 75% das visitas à página.

Embora alguns provedores de análise tenham suporte integrado para métricas do Core Web Vitals, mesmo aqueles que não devem incluir recursos básicos de métricas customizadas que permitem medir o Core Web Vitals em suas ferramentas.

Um exemplo disso é o [Web Vitals Report](https://github.com/GoogleChromeLabs/web-vitals-report) , que permite aos proprietários de sites medirem seus Core Web Vitals usando o Google Analytics. Para obter orientação sobre como medir os vitais essenciais da Web usando outras ferramentas analíticas, consulte [Práticas recomendadas para medir os vitais da Web no campo](/vitals-field-measurement-best-practices/) .

Você também pode relatar sobre cada um dos Core Web Vitals sem escrever nenhum código usando a [extensão Web Vitals do Chrome](https://github.com/GoogleChrome/web-vitals-extension) . Esta extensão usa a [biblioteca web-vitals](https://github.com/GoogleChrome/web-vitals) para medir cada uma dessas métricas e exibi-las aos usuários enquanto navegam na web.

Essa extensão pode ser útil para entender o desempenho de seus próprios sites, dos sites de seus concorrentes e da web em geral.

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals">web-vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals-extension">Extensão Web Vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

Como alternativa, os desenvolvedores que preferem medir essas métricas diretamente por meio das APIs da web subjacentes podem consultar estes guias de métricas para obter detalhes de implementação:

- [Medir LCP em JavaScript](/lcp/#measure-lcp-in-javascript)
- [Medir FID em JavaScript](/fid/#measure-fid-in-javascript)
- [Medir CLS em JavaScript](/cls/#measure-cls-in-javascript)

{% Aside%} Para obter orientação adicional sobre como medir essas métricas usando serviços analíticos populares (ou suas próprias ferramentas analíticas internas), consulte: [Melhores práticas para medir Web Vitals no campo](/vitals-field-measurement-best-practices/) {% endAside%}

#### Ferramentas de laboratório para medir os vitais essenciais da web

Embora todos os vitais essenciais da Web sejam, antes de mais nada, métricas de campo, muitos deles também são mensuráveis em laboratório.

A medição de laboratório é a melhor maneira de testar o desempenho dos recursos durante o desenvolvimento - antes de serem lançados para os usuários. É também a melhor maneira de detectar regressões de desempenho antes que elas aconteçam.

As seguintes ferramentas podem ser usadas para medir o Core Web Vitals em um ambiente de laboratório:

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://developers.google.com/web/tools/chrome-devtools">Chrome DevTools</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT em</a> vez disso)</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://developers.google.com/web/tools/lighthouse">Farol</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT em</a> vez disso)</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

{% Aside%} Ferramentas como o Lighthouse que carregam páginas em um ambiente simulado sem um usuário não podem medir o FID (não há entrada do usuário). No entanto, a métrica Total Blocking Time (TBT) é mensurável em laboratório e é um excelente proxy para FID. As otimizações de desempenho que melhoram o TBT no laboratório devem melhorar o FID no campo (consulte as recomendações de desempenho abaixo). {% endAside%}

Embora a medição em laboratório seja uma parte essencial da entrega de grandes experiências, ela não substitui a medição em campo.

O desempenho de um site pode variar drasticamente com base nos recursos do dispositivo do usuário, suas condições de rede, quais outros processos podem estar em execução no dispositivo e como eles estão interagindo com a página. Na verdade, cada uma das métricas do Core Web Vitals pode ter sua pontuação afetada pela interação do usuário. Apenas a medição de campo pode capturar com precisão a imagem completa.

### Recomendações para melhorar sua pontuação

Depois de medir os vitais essenciais da Web e identificar as áreas de melhoria, a próxima etapa é otimizar. Os guias a seguir oferecem recomendações específicas sobre como otimizar suas páginas para cada um dos Core Web Vitals:

- [Otimizar LCP](/optimize-lcp/)
- [Otimizar FID](/optimize-fid/)
- [Otimize o CLS](/optimize-cls/)

## Outros sinais vitais da web

Embora os vitais essenciais da Web sejam as métricas críticas para compreender e proporcionar uma ótima experiência ao usuário, também existem outras métricas vitais.

Esses outros Web Vitals frequentemente servem como proxy ou métricas suplementares para os Core Web Vitals, para ajudar a capturar uma parte maior da experiência ou para ajudar no diagnóstico de um problema específico.

Por exemplo, as métricas [Time to First Byte (TTFB)](/time-to-first-byte/) e [First Contentful Paint (FCP)](/fcp/) são aspectos vitais da *experiência de carregamento* e são úteis no diagnóstico de problemas com LCP ( [tempos de resposta](/overloaded-server/) lentos do servidor ou [recursos de bloqueio de renderização](/render-blocking-resources/) , respectivamente) .

Da mesma forma, métricas como [Total Blocking Time (TBT)](/tbt/) e [Time to Interactive (TTI)](/tti/) são medidas de laboratório que são vitais para detectar e diagnosticar possíveis *problemas de interatividade* que afetarão o FID. No entanto, eles não fazem parte do conjunto Core Web Vitals porque não são mensuráveis em campo, nem refletem um resultado [centrado no usuário.](/user-centric-performance-metrics/#how-metrics-are-measured)

## Evolução da vitalidade da web

Web Vitals e Core Web Vitals representam os melhores sinais disponíveis que os desenvolvedores têm hoje para medir a qualidade da experiência na web, mas esses sinais não são perfeitos e melhorias ou acréscimos futuros devem ser esperados.

O **Core Web Vitals** é relevante para todas as páginas da web e apresentado em ferramentas relevantes do Google. Mudanças nessas métricas terão um impacto de amplo alcance; como tal, os desenvolvedores devem esperar que as definições e limites do Core Web Vitals sejam estáveis e que as atualizações tenham um aviso prévio e uma cadência anual previsível.

Os outros Web Vitals são frequentemente específicos ao contexto ou à ferramenta e podem ser mais experimentais do que os Core Web Vitals. Como tal, suas definições e limites podem mudar com maior frequência.

Para todos os Web Vitals, as alterações serão claramente documentadas neste [CHANGELOG](http://bit.ly/chrome-speed-metrics-changelog) público.
