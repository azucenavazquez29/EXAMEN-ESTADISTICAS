# En esta practica podemos observar en la cual hice una coñexión con grafana de git 
# en la cual el usuario puede visualizar diferentes formas en estadisticas y configuyrar las api rest 

SELECT 
  DATE(h.clicked_at) AS time,
  COUNT(*)           AS clicks
FROM url_hits h
JOIN urls u ON u.id = h.url_id
WHERE u.code = '${code}'
GROUP BY DATE(h.clicked_at)
ORDER BY time;
