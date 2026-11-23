
self.addEventListener('push', event => {
  let data = {};

  try {
    data = event.data ? event.data.json() : {};
  } catch (e) {
    data = { title: 'LoveCircle Uganda', body: 'You have a new notification.' };
  }

  event.waitUntil(
    self.registration.showNotification(
      data.title || 'LoveCircle Uganda',
      {
        body: data.body || 'You have a new notification.',
        icon: './icon-192.png',
        badge: './icon-192.png',
        data: { url: data.url || './' }
      }
    )
  );
});

self.addEventListener('notificationclick', event => {
  event.notification.close();

  event.waitUntil(
    clients.openWindow(event.notification.data.url || './')
  );
});
